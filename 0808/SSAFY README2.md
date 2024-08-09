# ⛵ Story Boat 
### 공동 소설 제작 어플리케이션
StoryBoat는 WebRTC 기술을 활용한 실시간 협업 스토리텔링 플랫폼입니다. <br/>사용자들은 이 플랫폼을 통해 실시간으로 스토리를 구성하고, 플롯을 시각화하며, 아이디어를 공유할 수 있습니다.

주요 기능 <br/>
실시간 협업: WebRTC를 이용한 P2P 통신으로 빠르고 안전한 실시간 협업<br/>
스토리 플롯 시각화: ReactFlow를 사용한 직관적인 스토리 구조 시각화<br/>
동기화된 상태 관리: Recoil과 Yjs를 활용한 효율적인 상태 관리 및 동기화<br/>


---

## 목차

### 🐱 I. 팀원 정보 및 업무 분담 내역

### 📊 II. 설계 내용 (아키텍처 등) 및 실제 구현 정도

### 📑 III. 데이터베이스 모델링(ERD)

### 💻 IV. 서비스 대표 기능들에 대한 기술적인 설명

### ☄️ V. 트러블 슈팅  

### 💁 VI. 구현된 어플 DEMO 페이지 

### 🙇 VII. 느낀 점 및 참고사항


---

## 🐱 I. 팀원 정보 및 업무 분담 내역

- 프로젝트 기간 : 2024.07.02 ~ 2024.08.16 (약 7주)

<table>
  <tr>
    <th rowspan="3">Front</th>
    <td>박보람</td>
    <td>팀장, FE리더, Figma, UI/UX, React, 레이아웃</td>
  </tr>
  <tr>
    <td>김연지</td>
    <td>Figma, UI/UX, React, FE 기능 개발</td>
  </tr>
  <tr>
    <td>정소영</td>
    <td>React, 이미지 생성 AI, 텍스트 생성 AI</td>
  </tr>
  <tr>
    <th rowspan="1">Full Stack</th>
    <td>서한빈</td>
    <td>TechLeader, WebRTC 기능구현, SpringBoot, UCC</td>
  </tr>
  <tr>
    <th rowspan="2">Back</th>
    <td>이중현</td>
    <td>BE leader, JPA, SpringBoot</td>
  </tr>
  <tr>
    <td>김시온</td>
    <td>PM, CI/CD 구축, 인프라</td>
  </tr>
</table>


---

## 📊 설계 내용 (아키텍처 등) 및 실제 구현 정도

- **기술 스택 🔧**
![Skill](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EA%B8%B0%EC%88%A0%EC%8A%A4%ED%83%9D2.png?ref_type=heads)

|  | Front | Back | Infra |
| --- | --- | --- |  --- |
| **Language** | TypeScript | Java |  |
| **Framework** | React, Vite | Spring Boot, Spring Security |  |
| **Library** | WebRTC, Material-UI (MUI), Yjs<br/> Recoil, Styled-components, ReactFlow, Tailwind CSS<br/> React-i18next, React-speech-kit | Lombok  |  |
| **DB** |  | MongoDB, MariaDB |  |
| **Server** |  |  | Amazon EC2, Nginx, Docker |
| **Cloud Services** |  |  | AWS, Amazon S3 |
| **CI/CD Tools** |  |  | Jenkins |
| **AI** | SDXL(Stable Diffusion XL)<br/>DPO(Direct Preference Optimization) |  |  |

<br/>

### 협업 도구

#### Jira, Git & Github, Mattermost
![📎 Jira  ](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EC%A7%80%EB%9D%BC1.png?ref_type=heads).
![📎 Jira  ](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EC%A7%80%EB%9D%BC2.png?ref_type=heads).
![📎 Jira  ](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EC%A7%80%EB%9D%BC3.png?ref_type=heads).


## 프런트엔드 화면 디자인 설계
### 🎨 Figma 
[📎 Figma Link  ](https://www.figma.com/design/I7G6UwDk6q77acJHXI0o4J/ssafy-%EA%B3%B5%ED%86%B5?node-id=0-1&t=9wMHmHweJ2Ckecuf-1).


![Figma](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%ED%94%BC%EA%B7%B8%EB%A7%88.png?ref_type=heads)

메인 페이지, 랜딩 페이지, 로그인, 유저 프로필<br/>
스토리 작성, 스토리 편집, 캐릭터 관리, 스튜디오 관리, 팀 찾기 등 <br/>
계획했던 기능들을 모두 구현하였습니다.

## 백엔드 데이터 설계
### 📑데이터베이스 모델링 (ERD)
#### 📎 ERD Drawing 

![ERD 이미지](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/ERD1.png?ref_type=heads)
![ERD 이미지](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/ERD2.png?ref_type=heads)

#### 📎 Architecture

![Architecture](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EC%95%84%ED%82%A4%ED%85%8D%EC%B3%90.jpg?ref_type=heads)

### 🗂️ API 명세서 

#### 요구사항 명세서 
![요구사항 명세서1](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EC%9A%94%EA%B5%AC1.png?ref_type=heads)
![요구사항 명세서2](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EC%9A%94%EA%B5%AC2.png?ref_type=heads)
![요구사항 명세서3](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EC%9A%94%EA%B5%AC3.png?ref_type=heads)

#### 기능 명세서 
![기능명세서1](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EA%B8%B0%EB%8A%A5%EB%AA%85%EC%84%B81.png?ref_type=heads)
![기능명세서2](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EA%B8%B0%EB%8A%A5%EB%AA%85%EC%84%B82.png?ref_type=heads)
![기능명세서3](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EA%B8%B0%EB%8A%A5%EB%AA%85%EC%84%B83.png?ref_type=heads)

---
## 💻 서비스 대표 기능들에 대한 기술적인 설명 
### 1️⃣ WebRTC

![WebRTC](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/WebRTC1.png?ref_type=heads)

WebRTC는 웹 브라우저 간의 p2p 통신을 가능하게 하는 기술입니다. WebRTC는 연결 방식에 따라 Mesh, SFU, MCU 방식으로 구현할 수 있습니다. 서로 다른 클라이언트가 통신하기 위해선, 서로의 정보를 알아야 합니다. 이 정보를 조회하기 위해 Signal Server를 이용합니다.
<br/>
#### SignalServer

![WebRTC](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/WebRTC2.png?ref_type=heads)

클라이언트는 ICE를 통해 수집한 네트워크 연결 정보를 시그널 서버로 SDP로 전달합니다. ICE(Interactive Connectivity Establishment)는 피어 간의 최적의 경로를 찾아주는 프레임워크이며, 내부적으로 STUN을 통해 공인 IP와 포트를 조회합니다. 만약 방화벽 등으로 인해 직접 접근이 불가능한 경우, TURN을 통해 우회 접근할 수 있습니다. SDP(Session Description Protocol)는 ICE로 찾아낸 클라이언트 정보를 포함한 통신을 위한 정보를 송수신 하기 위한 프로토콜 입니다.Offer와 Answer를 통해 상호 연결을 시도하며, 이를 통해 클라이언트 간의 통신 경로가 설정됩니다. 시그널링 서버는 이 과정에서 필요한 정보를 중계하며, 연결이 성립된 이후에는 클라이언트 간의 직접 통신이 가능합니다.



### 2️⃣ SDXL - AI 텍스트 기반 이미지 생성 모델 

SDXL은 Diffusion 모델을 기반으로 하며, 큰 해상도를 가진 이미지를 생성하는 데 사용됩니다. Diffusion은 이미지 생성에 사용되는 확률적 생성 모델로, 이미지의 픽셀 값을 조금씩 변화시키면서 점진적으로 이미지를 생산합니다. 이 과정에서 노이즈가 이미지에 점진적으로 누적되면서  더 큰 해상도의 이미지를 생성할 수 있게 됩니다.

![SDXL1](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/SXDL1.jpg?ref_type=heads
)

저희는 이 과정에서 Segmind API를 사용하였습니다. COYO-700M과 LAION-2B에서 가져온 이미지-텍스트 쌍을 기반으로 대규모 데이터셋을 형성하였고, SDXL 모델을 활용하여 학습이 완료된 모델을 활용한 것입니다. 이 모델에 prompt를 입력하면, 텍스트에 기반한 이미지가 생성되며 더 정교한 설명을 할수록 원하는 이미지에 근접할 확률이 높아집니다 

![SDXL2](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/SXDL2.jpg?ref_type=heads)

### 3️⃣ 도커와 젠킨스

![도커와 젠킨스](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EB%8F%84%EC%BB%A4%EC%99%80%EC%A0%A0%ED%82%A8%EC%8A%A41.jpg?ref_type=heads)

간혹 맥북을 사용하는 친구들이 맥북이 불편하다며 윈도우를 깔아서 작업하는 광경을 볼 수 있습니다. 이 과정에서 사용하는 기술을 **가상머신(Virtual Machine, VM)이라고 합니다.**
**가상머신**은 **하이퍼바이저**라는 소프트웨어를 사용하여 호스트의 하드웨어 자원을 가상화하고, 여러 가상 운영 체제를 실행할 수 있게 합니다. 즉, 하이퍼바이저는 호스트 시스템의 하드웨어 자원을 분리하여 각각의 가상머신에 할당하고, 각 가상머신에 운영 체제를 별도로 설치해야 합니다.
반면, **도커**는 **컨테이너화(Containerization)** 기술을 사용하여 애플리케이션을 가볍고 효율적으로 실행합니다. 도커는 호스트 운영 체제의 **커널**을 공유하면서 애플리케이션을 독립된 환경에서 실행할 수 있도록 합니다. 이렇게 함으로써, 도커는 가상머신보다 더 적은 자원으로 애플리케이션을 실행할 수 있게 됩니다.

![도커와 젠킨스](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/%EB%8F%84%EC%BB%A4%EC%99%80%EC%A0%A0%ED%82%A8%EC%8A%A42.png?ref_type=heads)

*여기서 "가상화"란 자원을 독립적인 환경처럼 보이게 만들어주는 기술을 의미합니다.*
도커에서는 애플리케이션을 **이미지(Image)**라는 형태로 패키징하며, 이는 마치 애플리케이션의 설계도와 같습니다. 이 이미지를 실제로 실행 가능한 환경으로 변환한 것이 **컨테이너(Container)**입니다. 즉, 이미지를 컨테이너로 변환하여 실행합니다. 그리고 이러한 이미지는 이미 많은 사람들이 생성해 놓았기 때문에, 우리는 기존의 이미지를 감사하게 가져다 사용하면 됩니다. Jenkins는 소프트웨어 구축, 테스트, 배포와 관련된 모든 종류의 작업을 자동화하는 데 사용할 수 있는 독립형 오픈 소스 자동화 서버입니다. Jenkins는 기본 시스템 패키지, Docker를 통해 설치하거나 Java Runtime Environment(JRE)가 설치된 모든 시스템에서 독립 실행형으로 실행할 수 있습니다.

---
## ☄️ 트러블 슈팅
### 1️⃣ Build Error
1. no main manifest attribute, in app.jar
**build.gradle**
```
bootJar {
	enabled = true
}
jar {
	enabled = false
}

```
Plain jar vs Executable jar
**bootJar** : 라이브러리, 의존성이 포함된 Jar 파일을 생성하는 옵션
**jar** : 일반적인 jar 파일로 실행 가능한 형태가 아님!, 주로 라이브러리 JAR 파일 만들때 실행
- 둘 다 `true`로 설정할 경우, Docker build시 에러 발생
    
    ```bash
    # Dockerfile
    ...
    ARG JAR_FILE=build/libs/*.jar
    COPY ${JAR_FILE} app.jar
    ...
    # *를 특정 jar 파일명으로 수정하거나 bootJar만 빌드하도록 설정
    ```
 만약 `bootJar`를 `true`로 설정하고 `java -jar` 를 실행할 경우 에러 발생.
 no main manifest attribute, in {jar 파일명}.jar
    

2. Manifest duplicated
    
빌드 과정에서 물리적으로 두 개의 `MANIFEST.MF` 파일이 존재하지는 않지만, 여러 종속성이나 라이브러리가 각각 자신의 `MANIFEST.MF` 파일을 포함하고 있을 수 있습니다. 빌드 도구인 Gradle은 이 파일들을 병합하거나 복사하는 과정에서 중복된 항목을 처리해야 합니다.
    
`DuplicatesStrategy`를 설정하지 않으면, Gradle은 기본적으로 중복된 파일을 모두 포함하려고 하며, 이로 인해 빌드 과정에서 충돌이 발생할 수 있습니다. 따라서, `DuplicatesStrategy.EXCLUDE` 설정을 통해 중복 파일을 무시하고 첫 번째 파일만 포함하도록 지정함으로써 이러한 충돌을 방지할 수 있습니다.
    
다음은 `DuplicatesStrategy` 설정을 통해 빌드를 성공시키는 일반적인 방법입니다:
    
1. **`build.gradle` 파일에서 설정**:
        
        ```groovy
        groovy코드 복사
        bootJar {
            duplicatesStrategy = DuplicatesStrategy.EXCLUDE
        }
        
        ```
        
2. **기본적으로 병합 과정에서 발생하는 중복 처리**: 여러 종속성에서 동일한 파일을 포함하려 할 때 발생하는 문제를 방지합니다. 이 경우, 처음 발견된 파일만 포함하고 나머지는 무시합니다.
3. **빌드 성공**: 중복 파일로 인한 충돌이 발생하지 않으므로 빌드가 성공적으로 완료됩니다.
    
여기서 중요한 점은 실제로 동일한 파일(예: `MANIFEST.MF`)이 여러 번 포함되려고 하는 상황이 발생할 수 있다는 점입니다. 이 경우, 중복 전략을 설정하지 않으면 Gradle이 충돌을 일으킬 수 있습니다. 따라서, `DuplicatesStrategy.EXCLUDE` 설정은 이러한 문제를 해결하는 데 매우 유용합니다.

### 2️⃣ ForwardedheaderFilter

로컬 서버에서 개발시 문제가 없으나 nginx 안의 Proxy 환경에서 문제가 발생했을 경우 해당 Filter를 확인!

→ Proxy 환경에서는 ForwardedHeaderFilter 가 실행되서 HTTP 요청의 `Forwarded` 헤더 또는 `X-Forwarded-*` 헤더를 처리하여 원래의 요청 정보를 복원해야 한다!

하지만! 해당 Filter 는 Spring Security 필터 체인에 기본적으로 포함되지 않는 Filter

주로  Spring MVC, Spring Boot 의 웹 애플리케이션에서 Proxy 서버나 로드 밸런서 뒤에 있는 클라이언트의 원래 요청 정보를 복원하기 위해 사용됨!

따라서 우리는 해당 Filter를 등록해 우선순위를 보안 필터 체인보다 먼저 실행되게 세팅해야 한다!

```java
import org.springframework.boot.web.servlet.FilterRegistrationBean;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.web.filter.ForwardedHeaderFilter;
import org.springframework.core.Ordered;

@Configuration
public class FilterConfig {

    @Bean
    public FilterRegistrationBean<ForwardedHeaderFilter> forwardedHeaderFilter() {
        FilterRegistrationBean<ForwardedHeaderFilter> bean = new FilterRegistrationBean<>();
        bean.setFilter(new ForwardedHeaderFilter());
        // 필터 적용의 위치를 가장 초기 위치에 적용!
        bean.setOrder(Ordered.HIGHEST_PRECEDENCE);
        return bean;
    }
}
```

#### 상세 흐름 (X-Forwared-* : XFF)

실제 백엔드는 8080 포트에서 동작합니다. 이 포트를 외부 도메인에 직접 노출시키는 것은 적절하지 않습니다. 8080 포트는 Docker 내부 컨테이너 접근에만 사용되며, 클라이언트가 외부에서 이 포트로 직접 접근하는 것은 본인의 로컬호스트의 8080 포트로 접근하는 것이 되기 때문입니다. 대신 프록시 서버(Nginx)가 외부 도메인과 내부 Docker 컨테이너 간의 요청을 중계합니다.

Nginx는 외부 도메인(`i11c107.p.ssafy.io`)과 내부 Docker 컨테이너(`localhost:8080`) 사이의 프록시 역할을 하여 클라이언트가 도메인으로 접근하면 Nginx가 이를 내부 Docker 컨테이너로 전달합니다. Docker 컨테이너 내부 포트(8080)는 외부 호스트의 다른 포트인 8082(blue), 8081(green)로 번걸아가며 매핑됩니다. 클라이언트는 외부 도메인에 접속하고, Nginx는 이 요청을 내부 Docker 컨테이너로 전달하는 것입니다.

이를 통해 클라이언트는 Docker 컨테이너의 내부 포트를 직접 접근하지 않고도 프록시 서버를 통해 안전하게 애플리케이션에 접근할 수 있습니다. `X-Forwarded-*` 헤더를 통해 클라이언트의 원래 요청 정보가 전달되며, Spring Boot 애플리케이션은 이를 인식하여 올바른 URL을 처리할 수 있게 됩니다.

이를 위해 nginx는 다음과 같은 설정이 있습니다.

```
location /api/ {
	proxy_pass 127.0.0.1:8080;
	...
  proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  proxy_set_header X-Forwarded-Proto $scheme;
  ...
}
```

**proxy_set_header X-Forwarded-Proto $scheme**

클라이언트의 프로토콜(HTTP, HTTPS)를 `$scheme`에 담아서  proxy_pass에 명시한 서버에 전달

**proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for**

클라이언트의 실제 IP 주소를 `$proxy_add_x_forwarded_for` 담아서 proxy_pass 서버에 전달

최종적으로, `i11c107.p.ssafy.io`에서 `/api` 경로에 접근할 경우, 다음과 같은 헤더가 내부 컨테이너의 8080 포트에서 실행 중인 백엔드 서버로 전송됩니다.

최종 X-Forwarded-* 헤더

```bash
X-Forwarded-For: i11c107.p.ssafy.io
X-Forwarded-Proto: https
```

Spring Boot는 이 정보를 기반으로 필터를 통해 원래 요청된 URL을 올바르게 처리합니다.

---

## 💁 구현된 어플 DEMO 페이지 
### 1️⃣ 메인페이지
![메인페이지](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/1.%EB%A9%94%EC%9D%B8%ED%8E%98%EC%9D%B4%EC%A7%80.png?ref_type=heads)
<br><br>네비게이션바를 사용해서 반응형으로 제작
<br>
### 2️⃣ 로그인 페이지 
![로그인 페이지](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/2.%EB%A1%9C%EA%B7%B8%EC%9D%B8,%20%ED%9A%8C%EC%9B%90%EA%B0%80%EC%9E%85.png?ref_type=heads)
<br><br>SNS 소셜 로그인 기능 구현 
<br>
### 3️⃣ 프로필 페이지
![프로필 페이지](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/3.%20%ED%94%84%EB%A1%9C%ED%95%84.png?ref_type=heads)
<br><br>회원의 기본 정보를 출력
<br>

### 4️⃣ 스토리 작성 
![스토리 작성1](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/4.1%20%EC%8A%A4%ED%86%A0%EB%A6%AC%20%EC%9E%91%EC%84%B1.png?ref_type=heads)
![스토리 작성2](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/4.2%EC%8A%A4%ED%86%A0%EB%A6%AC%20%EC%9E%91%EC%84%B1.png?ref_type=heads)
<br> CRUD 기능 구현
<br>
### 5️⃣ 팀 찾기 
![팀 찾기1](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/5.1%20%ED%8C%80%20%EC%B0%BE%EC%95%84%EB%B3%B4%EA%B8%B0.png?ref_type=heads)

### 6️⃣ 팀원 모집 및 초대
![팀원 모집](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/5.2%20%ED%8C%80%EC%9B%90%EB%AA%A8%EC%A7%91.png?ref_type=heads)
![팀원 초대](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/5.3%20%ED%8C%80%EC%9B%90%20%EC%B4%88%EB%8C%80%ED%95%98%EA%B8%B0.png?ref_type=heads)
<br><br>초대코드 전송기능 추가
<br>
### 7️⃣ 캐릭터 보관함
![캐릭터 보관함1](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/6.1%20%EC%BA%90%EB%A6%AD%ED%84%B0%20%ED%8E%98%EC%9D%B4%EC%A7%80.jpg?ref_type=heads)
![캐릭터 보관함2](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/6.2%20%EC%BA%90%EB%A6%AD%ED%84%B0%20%ED%8E%98%EC%9D%B4%EC%A7%80.jpg?ref_type=heads)
![캐릭터 보관함3](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/6.3%20%EC%BA%90%EB%A6%AD%ED%84%B0%20%ED%8E%98%EC%9D%B4%EC%A7%80.jpg?ref_type=heads)
<br><br>캐릭터 카드 생성, 이미지 업로드 및 수정기능
 <br>
### 8️⃣ AI 글쓰기, 그림그리기 
![그림그리기](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/AIpainting.gif?ref_type=heads)
![글쓰기](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/AIwritting.gif?ref_type=heads)
<br> AI를 활용한 글쓰기 및 그림그리기 
<br> 
<br>

### 9️⃣ 구독 플랜 
![구독플랜](https://lab.ssafy.com/s11-webmobile1-sub2/S11P12C107/-/raw/Readme_image/README_IMG/8%20%EA%B5%AC%EB%8F%85%ED%94%8C%EB%9E%9C.png?ref_type=heads)

<br> 구독 및 요금제 업그레이드 기능 추가 

---
## 🙇 느낀점

<table>
  <tr>
    <th rowspan="3">Front</th>
    <td>박보람</td>
    <td>느낀점💡</td>
  </tr>
  <tr>
    <td>김연지</td>
    <td>느낀점💡</td>
  </tr>
    <tr>
    <td>정소영</td>
    <td>6인팀 프로젝트를 진행하면서, 저에게 협업과 소통 능력이 부족함을 깨닫게 되었습니다. 처음 팀을 만났을  때, ice breaking으로 이야기를 많이 나누어야 한다는 것. 이것을 잘하고 친화력이 뛰어난 팀원과 만나게 되어 감사합니다. 또, Git을 능숙하게 다룰 줄 알아야 다른 팀원들의 작업에 영향을 주지 않다는 것을 경험을 통해 배우게 되었습니다.<br/><br/>개발 분야에 있어서는 최신 기술인 React를 활용해서 프로젝트를 진행할 수 있어서 좋았고, API 명세서에 따라 DB의 자료를 불러오고 표출시키는 과정에서 배울점이 많았습니다. 또한, 개인적으로 웹개발을 할 때는 주로 cloudtype이나 dothome과 같은 호스팅 서비스를 사용했는데, 이번에 AWS나 docker, Jenkins를 활용해서 배포하는 방법에 대해 공부해보고 싶다는 생각이 들었습니다.(같은 팀 백엔드분께서 문서 정리를 잘해주셔서 감사)<br/><br/>AI를 활용한 개발도 무척 재미있었습니다. 예전에는 주로 CNN이나 CGCNN 같은 물질 과학 분야에 특화된 모델을 많이 다루었는데, 이번에는 개발자의 입장에서 Text To Image 모델(SDXL)이나 LSTM, DPO와 같은 조금 더 대중적인 목표를 가진 모델에 대해 공부하고 활용해볼 수 있어서 유익했던 것 같습니다. SSAFY 덕분에, 개발자로서도 개인으로서도 크게 성장하고 있음을 느끼고 있습니다. 감사합니다 
    </td>
  </tr>
  <tr>
    <th rowspan="1">Full Stack</th>
    <td>서한빈</td>
    <td>느낀점💡</td>
  </tr>
  <tr>
    <th rowspan="2">Back</th>
    <td>이중현</td>
    <td>느낀점💡</td>
  </tr>
  <tr>
    <td>김시온</td>
    <td>느낀점💡</td>
  </tr>
</table>

---
### 참고사항
#### ① 도입배경
기존 서비스들과 차별화된 소설 제작 사이트를 제작해보자 

#### ② 기획의도 
Story Boat는 소통 기반 협업 소설 작성 플랫폼<br/>
실시간 음성 통화, 아이디어 플롯 회의, 공동 작성 기능을 지원함.<br/>
소설을 공동으로 집필하고, 원고의 버전을 관리할 수 있음<br/>
AI를 활용한 캐릭터 이미지 생성 및 글쓰기 기능까지 가능하도록

#### ③ 기대효과
작가들의 협업 강화 - 작가들이 팀을 구성하고 협력하여 창작물 작성 <br/>
효율적인 작업 관리 - 버전 관리를 통해 효과적으로 자원 관리 <br/>
단계별 권한 설정 - 편집자를 작업 공간에 초대하여 피드백 제공
