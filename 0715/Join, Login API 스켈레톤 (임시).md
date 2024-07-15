| 기능 | URL | 요청(Json) | 응답 | 설명 | 메서드 |
| --- | --- | --- | --- | --- | --- |
| 회원가입 | http://localhost:8080/join | // Body
{
"username":"ID",
"password":"PW"
} | Body: ok | 권한 존재 X
토큰 불필요 | POST |
| 로그인 | http://localhost:8080/login | // Body
{
"username":"ID",
"password":"PW"
} | 성공시: 200
Header: Authorization (Access Token)
Cookie: refresh (Refresh Token)

Access 토큰 10분단위 만료
Refresh 토큰 24시간 만료  | 권한 존재 X
토큰 불필요 | POST |
| 로그아웃  | http://localhost:8080/logout | // Cookie
Refresh Token을 
refresh: [~] 로 | 성공시: 200 | Refresh Token 필요 | POST |
| 권한 화면  | http://localhost:8080/admin | // Header
AccessToken을 
Authorization: [~] 로 | Body: Admin | Access Token 필요 | POST |
| 메인 화면 | http://localhost:8080/login |  | Body: Main  | 권한 존재 X
토큰 불필요 | GET |
| Access Token 만료시  | http://localhost:8080/reissue | // Cookie
Refresh Token을 
refresh: [~] 로 | 성공시: 200
Header: Authorization (Access Token) | Refresh Token 필요 | POST |

## 기본 세팅법

1. **Workbench 설치 후 User 추가**
    - Users and Privileges 에서 add Account
        - User: newuser1 (이름 변경 안될경우 add Account 2번하면 자동으로 세팅됨)
        - PW: q1w2e3r4!
        - 권한 → 우선 기본적인 SELECT, INSERT, DELETE, UPDATE 이상으로 추가!
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5177a4df-080c-444a-bee8-4644fc74314b/c48ccf43-fc86-4980-9b09-2f2e405e1330/Untitled.png)
    
2. **SCHEMA 생성**
    - **SpringSecurity** 로 DB(Schema 생성)
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5177a4df-080c-444a-bee8-4644fc74314b/dc22f172-b727-4f65-b778-8d05857e903e/Untitled.png)
    
3. **jar 파일 경로에서 `java -jar [파일명.jar]` 명령어 실행해 프로젝트 실행**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/5177a4df-080c-444a-bee8-4644fc74314b/b082d6b6-55d0-4d7b-8729-01318abcbf2f/Untitled.png)

1. 종료시 Ctrl + C

## 보안을 위한 JWT 진화

1. **싱글 JWT 토큰 → 매 요청마다 JWT 토큰이 전송되므로 탈취되었을 경우 대비 로직이 존재**
2. **다중 토큰 : Refresh 토큰과 생명주기**
    - 자주 사용되는 토큰(Access) 과 재발급 토큰 (Refress) 토큰 2개 발급하기!
        - Access 토큰 : 권한이 필요한 모든 요청 헤더에 사용될 JWT로 탈취 위험을 낮추기 위해 약 10분 정도의 짧은 생명주기를 가진다.
        - Refresh 토큰 : Access 토큰이 만료되었을 때 재발급 받기 위한 용도로만 사용되며 약 24시간 이상의 긴 생명주기를 가진다.
    - 권한이 필요한 모든 요청은 Access 토큰을 통해 요청
        - 권한이 맞을때, 토큰이 만료된 경우 → 발급받은 Refress 토큰으로 검증후 Access 토큰 재발
    - 이를 구현하는법
        1. 로그인 시 Server → Front 에게 Access/Refresh 토큰 2개 발급
        2. Access 토큰으로 통신중 토큰이 만료된 경우 → 서버측에서 서로 합의된 응답 보냄
        3. 이를 받은 프론트 단에서 Refresh 토큰 전송해 새로운 Access 토큰 발급받음 
            - 서버에선 Refresh 토큰을 받을 엔드포인트(Controller) 등록해 처리!
3. **Refresh토큰이 탈취되는 경우**
    - Front 에서의 토큰 저장 위치를 고려 (로컬/세션 스토리지)
        - 로컬스토리지: xss 공격에 취약 → Access 토큰 저장시키기
        - httpOnly 쿠키: CSRF 공격에 취약함 → Refresh 토큰 저장 이  일반적임…
    - Refresh 토큰 Rotate → Refresh 토큰도 재발급하기?
        - 생명주기가 긴 Refresh토큰에 대한 서버측 해결책
4. **로그아웃과 Refresh 토큰 주도권**
    - 로그아웃시 Front단에서는 Access/Refresh 토큰 제거 **but** Server측 주도권이 없어 생명주기 동안 방어할 수단이 없음!!
        - 서버측에도 Refresh토큰을 별도 저장소에 저장(DB), 로그아웃시 삭제
        - 이를 통해 JWT 토큰에 대한 주도권을 서버에서도 가질 수 있음
        - **Refresh토큰 블랙리스팅**
5. **로그인 시 메일 알림 (추가적)**
    - 본인이 아닐경우 아니요 요청시 서버의 Refresh토큰을 지워 인증 막기 가능!
