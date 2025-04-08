# Portfolio

<div style="display: flex; align-items: center;">
  <img src="https://github.com/user-attachments/assets/4b0df2e1-ddb3-4da4-9d35-15af4f18bdda" alt="양승필" style="margin-right: 20px;">
  <div>
    <h1>양승필</h1>
    <p>생년월일 : 1999.03.31</p>
    <p>Email : yang_seongp31@naver.com</p>
    <p>GitHub : https://github.com/yangsp31</p>
    <p>기술 블로그 : https://velog.io/@yang_seongp31/series</p>
    <br>
    <p>패킷 단위로 나뉜 데이터가 네트워크를 통해 전달되어 재조립되고, 백엔드에서 의미 있는 데이터로 구조화되고 정제된 뒤, DB에 저장되거나 다시 네트워크를 통해 전달되는 과정을 보며 그 흐름에 흥미를 느꼈습니다.</p>
  </div>
</div>
<br>

# 설계부터 하는 개발자
대규모 프로젝트를 직접 경험해보진 않았지만, 저는 작은 프로젝트라도 항상 전체 구조와 데이터 흐름을 설계하는 것부터 시작합니다.
<br><br>

### 설계의 중요성을 느낀 계기
처음에는 설계 없이 바로 코드를 작성하면서 개발을 시작했지만, 오류가 자주 발생했고 기능 하나를 수정하려 해도 전체 코드를 확인해야 하는 상황이 반복되었습니다.

이 경험을 통해 “집을 짓는 데 설계도가 필요하듯, 프로그램도 반드시 설계가 먼저다”라는 교수님의 말씀이 깊이 와닿았습니다.

그 이후로는 어떤 프로젝트든 흐름도, ERD, 아키텍처 다이어그램을 먼저 그려보는 습관이 생겼습니다.
<br><br>

### 설계의 효과
아직 정석적인 아키텍처 설계 방법이나 유연한 구조 설계를 완전히 이해한 것은 아니지만, 직접 만든 아키텍처 다이어그램을 바탕으로 요구사항에 맞는 기능과 데이터 처리 방식, 저장 구조 등을 시각화해보면서 구현시에도 방향을 잃지 않고 계획대로 진행할 수 있었습니다.

또한, 구조를 고민하며 설계를 하다 보면 필요한 기술과 환경을 파악할 수 있었고, 그 과정에서 어떤 기술을 선택해야 할지, 어떻게 활용해야 더 효율적으로 구현할 수 있을지도 함께 고민할 수 있었습니다. 그 결과, 구현 중간에 필요한 기술을 즉흥적으로 추가하여 프로젝트 기간이 늘어나거나, 전체 구조를 다시 수정해야 하는 상황을 줄일 수도 있었습니다.

이처럼 프로젝트 진행시 구조를 먼저 고민하고 설계해보는 습관을 통해, 문제를 예측하고, 더 나은 방향을 설계하는 개발자로 성장하고 있다고 느끼고 있습니다.
<br><br>

### 직접 그린 설계도 예시자료
![ReLife Architecture](https://github.com/user-attachments/assets/ef0f03f2-059b-4ee6-958f-75a174daf31d)
 * 외부 API의 응답이 Webhook 방식으로 들어오는 환경에서, Redis와 S3를 활용한 백엔드 처리와 Next.js 기반 프론트엔드에서의 Polling을 사용하여 실시간 데이터 전달을 고려한 설계 예시
<br><br>

# 기술의 이유를 묻고, 구조에 질문을 던집니다.
저는 프로젝트를 설계하고 구현할 때마다 왜 이 기술을 선택했는가, 이 구조가 정말 최선일까 라는 질문을 스스로에게 던지며 고민합니다.

그 이유는, 단순히 기능이 작동하는 것에 만족하지 않고, 더 나은 방법을 고민하고 적용하는 과정이 진짜 프로젝트를 완성하는 것이라 생각하기 때문입니다.

그렇기에, 프로젝트가 끝나더라도 저는 그 고민을 끝내지 않습니다. 충분히 만족할 만큼 고민하고 개선되지 않았다면, 저는 그것을 완성했다고 생각 하지 않기 때문입니다. 그래서 회고를 통해 구조와 기술을 다시 확인하며, 더 나은 선택이 있었는지 고민합니다.
<br><br>

### 회고의 예시
실제로 몇 년 전 진행한 프로젝트를 회고하며, 당시의 구조 선택이 최선이 아니었음을 깨달은 경험이 있습니다. 당시에는 주기적인 크롤링을 위해 Flask 서버를 별도로 구축했고, 앱에서 환율 및 최다 검색 기업명을 실시간으로 요청하면 SpringBoot가 해당 요청을 Flask로 전달하고, Flask가 실시간으로 크롤링을 수행하여 다시 데이터를 앱으로 전달하는 구조였습니다.

이 방식은 요청이 많아질 경우, 모든 요청에 대해 매번 크롤링을 수행해야 했고, 그 결과 Flask 서버에 과도한 부하가 발생할 수 있으며, 최악의 경우 모든 요청을 정상적으로 처리가 불가하다 판단 하였습니다. 

실제로 로컬환경에서 크롤링 진행시 발생하는 부하를 고려한 테스트 로직을 구현한 Flask를 구축 후 apache-jmeter로 테스트 진행시, 예상한 결과가 발생 하였습니다.
<br><br>

### 부하테스트
로컬PC 환경에서 임의로 테스트한 결과임으로 실제와 오차가 존재할수 있음.

![부하테스트](https://github.com/user-attachments/assets/791e3d41-012d-4681-b5f1-33a3a6ff459b)
<br><br>

### 테스트용 Flask 로직

```from flask import Flask, jsonify
import random
import time

app = Flask(__name__)

# 최다 검색 기업명과 환율을 가정한 데이터 생성
def generate_random_companies():
    companies = ["Company A", "Company B", "Company C", "Company D", "Company E"]
    return random.choice(companies)

def generate_random_exchange_rates():
    return {
        "USD_TO_EUR": random.uniform(0.8, 1.2),
        "USD_TO_JPY": random.uniform(100, 150),
        "USD_TO_GBP": random.uniform(0.7, 1.0),
    }

# 부하를 발생시키는 로직
def simulate_heavy_load():
    # 일부러 CPU 부하를 발생시키는 루프
    result = []
    for _ in range(10000):  # 10000번 반복하여 계산량 증가
        result.append(generate_random_companies())
        result.append(generate_random_exchange_rates())
    return result

@app.route('/', methods=['GET'])
def start_load():
    try:
        data = simulate_heavy_load()

        # 부하 작업이 끝난 후 결과를 반환
        return jsonify({
            "status": "success",
            "data": data[:5],
        }), 200
    except Exception as e:
        return jsonify({'error': str(e)}), 500

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0', port=5000, threaded=True)
```
<br><br>

### 회고의 결론
이러한 점을 고려하였을때 개선방안을 다음과 같이 생각 하였습니다:

 * 환율과 최다 검색 기업명 데이터를 1분 ~ 10분 단위로 주기적으로 수집하여, DB나 Redis에 저장한 뒤, 사용자의 요청 시 SpringBoot가 이를 직접 조회해 응답하는 구조

 * 외부 API를 앱에서 직접 호출하도록 하여 서버 사이드 부담을 줄이고 전체 구조를 간소화하는 방식

위와 같은 방법들로 구축하였다면, Flask 서버 없이 배치 서버로 단순화할 수 있었고, 실질적인 요청 처리도 SpringBoot에서 모두 가능했을 것입니다.
<br><br>

### 저는 기술의 이유를 묻고, 구조에 질문을 던집니다.
이처럼 프로젝트가 끝난 후에도 계속해서 왜 이 기술을 선택하였는지, 이 구조가 최선인가에 대한 고민을 통해 유사한 상황에서 더 나은 선택을 할 수 있는 생각의 폭을 키울수 있었습니다.
<br><br>

# Skill

### Language

* JAVA

  * 기본 문법 이해 수준.
  * 간단한 SpringBoot 프로젝트에 활용함.
  * Swing을 활용하여 간단한 응용프로그램 개발 경험이 있음.

* Python
  
  * 기초적인 문법 이해 수준.
  * OpenCV와 Flask를 활용한 간단한 프로젝트 경험이 있음.
<br>
  
### Back-End

* SpringBoot
  
  * 기본적인 구조와 설정 이해 수준.
  * JPA를 사용한 간단한 CRUD 기능과 엔티티 매핑 구현 경험이 있음.
  * OAuth2을 이용한 기초적인 소셜 로그인 구현 시, Spring Security를 기초 수준에서 활용한 경험이 있음.
  * 기초적인 JWT 발급, 인증/인가 과정을 구현해본 경험이 있음.
 
* AWS EC2

  * 인스턴스를 생성하고, 기본적인 설정 및 Springboot 프로젝트를 배포한 경험이 있음.
  * Nginx를 설치하여 기초적인 리버스 프록시 설정에 대한 경험이 있음.
  * Let's Encrypt를 활용한 기초적인 HTTPS(SSL 인증서) 적용 경험이 있음.
  * Docker와 Docker Compose를 활용해 프로젝트를 컨테이너화하고 실행/배포해본 기초적인 경험이 있음.
  <br>

### Database

* MySql

  * 기본적인 SQL 문법을 활용하여 간단한 테이블을 생성하고, SELECT, INSERT, UPDATE 등 기초적인 쿼리를 작성해본 경험이 있음.
  * 기본적인 수준에서 요구사항을 반영한 ERD 설계와 테이블 생성을 해본 경험이 있음.

* AWS S3

  * S3 버킷 생성 및 간단한 파일 업로드/읽기 권한 설정 경험 있음.
  * SpringBoot 프로젝트에서 기초적인 이미지 업로드 기능을 구현한 경험이 있음.
  <br>
 
### Front-End

* Next.js

  * CSR을 이용한 기본적인 웹 페이지를 구성해본 경험이 있음.
  * API Route를 이용한 기초적인 백엔드 로직 처리 경험이 있음.
  <br>
  
### ETC

* React Native

  * Expo를 활용해 간단한 모바일 앱을 만들고, 기초적인 UI 화면을 구성해본 경험이 있음.
 
* Git

  * Git을 이용한 버전 관리 및 GitHub를 활용한 협업 경험 있음.
  * Git을 활용해 브랜치 생성, Pull/Push, GitHub 연동 등 기본적인 작업을 경험해보았으며, 버전 관리의 기초적인 흐름을 이해하는 수준.
    <br><br><br>

# 프로젝트
* DrawD - OLED 다이어그램 작성 웹 서비스
* DrawD Desktop - OLED 다이어그램 작성 응용프로그램
* ReLife - 인테리어 시뮬레이션 웹 서비스
<br><br><br>

## DrawD - OLED 다이어그램 작성 웹 서비스 (2025.02.03. - 2025.02.25.) (1인 프로젝트)

### 개요

디스플레이 분야, 특히 OLED를 연구하는 대학원생의 연구 및 문서 작업 효율성을 높이기 위한 웹 서비스입니다.

사람이 손으로 그린 도식보다 정밀하고 객관적인 다이어그램을 작성할 수 있도록 지원하며, 실험 설계 단계나 연구 내용을 설명할 때 시각적 근거 자료로 활용될 수 있도록 개발 하였습니다.

웹 서비스로 제공함으로써, 별도의 설치 과정 없이 언제 어디서나 접근이 가능하며, 사용자가 편리하고 직관적으로 다이어그램을 작성할 수 있도록 구성되었습니다.
<br><br>

### Architecture & ERD

![DrawDrealArc](https://github.com/user-attachments/assets/2415eaed-34ef-4293-a4a0-ee0eb794d967)
<br><br>

![DrawD Server Architecture drawio](https://github.com/user-attachments/assets/5207e3d2-45c5-455c-a6e8-eff7074b34a8)
<br><br>

![DrawD ERD](https://github.com/user-attachments/assets/4b11b376-fe2f-4076-9e1f-2056b4a0375b)
<br><br>

### 사용기술

* SpringBoot (Spring Security, OAuth2 Client, JPA, jwt, json schema validator)
* Next.js (uuid)
* MySql
* AWS (EC2, Route 53, NginX, Docker, Docker Compose)
* Google OAuth
<br>

### 개발내역

* 구글 로그인 구현

  * SpringBoot의 oauth2-client를 사용하여 구글 로그인 요청시 인가 코드와 엑세스 토큰을 모두 서버에서 처리하도록 하였음. 클라이언트에서 인가 코드를 서버로 전송할 때 탈취문제를 줄이기 위해 이 방식을 선택하였음.
 
  * SpringBoot Security를 사용하여 인증/인가 흐름을 설정하고, 로그인 성공 후 JWT를 생성해 클라이언트에게 반환하는 커스텀 로그인 성공 핸들러와, JWT 검증을 담당하는 커스텀 필터를 등록하여 인증/인가를 구현함.
 
  * 처음 구글 로그인 시 인증/인가 관리 및 유저별 데이터 관리를 위해 유저의 email, profile, 이름을 MySQL에 저장함.
 ----
* JWT 발급과 인증/인가, 갱신 구현

  * Spring Security에 등록된 커스텀 로그인 성공 핸들러에서 jjwt를 사용하여 사용자 이름, email, 암호화 키를 사용하여 JWT를 발급함.
  
  * 암호화 키는 랜덤하게 제공되는 AES-128-CBC 암호화 알고리즘을 사용하여 암호화 하고 Base64로 인코딩된 키을 사용하였으며, 키값 2개를 이어붙여 JWT가 탈취되어도 사용자 정보 취득을 조금이라도 더 어렵게 하기 위해 64자의 암호화 키를 사용함.
 
  * 유효기간이 상당히 짧은 AccessToken과 유효기간이 길지만 빈번하게 사용되지 않는 RefreshToken 2개의 JWT를 만들어, AccessToken이 탈취 되더라도 짧은 유효 기간으로 인해 피해를 최소화하고, AccessToken을 갱신하는 RefreshToken을 통해 지속적인 인증을 유지할 수 있도록 구현함.
 
  * RefreshToken을 DB에 저장하여 사용자 별로 관리하며, 커스텀 JWT 필터를 통해 이를 검증하고, 추가로 저장된 RefreshToken과 대조하도록 구현함. RefreshToken은 긴 유효 기간을 가지므로 탈취 시 큰 보안 위험이 발생한다고 판단함.
    따라서 RefreshToken을 서버 측에서 관리하여 간편한 무효화, 갱신 및 관리가 가능해짐. 그렇기에 서버 무상태라는 JWT의 장점을 포기하고, 보안성을 높이는 방향으로 구현함.

  * AccessToken과 RefreshToken이 서버로 들어왔을 때, 각각의 비밀키를 사용하여 JWT 서명을 검증한 후, JWT에 있는 사용자 정보를 기반으로 DB 조회를 통해 인증 및 인가 과정을 진행함.
 
  * 유효기간이 만료된 AccessToken을 포함한 요청이 서버로 들어올 경우 RefreshToken을 포함해서 갱신요청을 보내라는 응답을 하고, 만일 RefreshToken도 만료되었다면 재로그인을 하도록 응답을 보내도록 구현함.
 
  * RefreshToken의 유효기간이 짧게 남아 있을 경우, 자동으로 재발급하여 사용자가 주기적으로 로그인을 하지 않도록 구현함.
 
  * 모든 JWT는 발급/재발급시 Cookie에 담아 반환하도록 구현함. Response Body에 담아 반환하는것 보다 탈취의 위험이 적다고 판단함. 로그인시 발급된 JWT는 리다이렉션과 함께 반환 하도록 하였음.
 
  * **전체적인 JWT 흐름도**
  
  ![JWT 흐름png](https://github.com/user-attachments/assets/7479c1e5-daff-43fe-a181-a092e3370670)
----
* MySql과 JPA를 사용한 사용자별 다이어그램 데이터 CRUD 구현

  * 테이블은 사용자의 정보를 담는테이블, 그려진 다이어그램의 메타 데이터를 담는 테이블, 실질적으로 다이어그램을 그릴수 있는 JSON 형식의 문자열로 된 다이어그램 데이터 테이블, 독립 테이블로서 재료의 고유값들을 담고있는 재료 테이블 총 4개를 설계하였음.
 
  * **ERD**
  
   ![DrawD ERD](https://github.com/user-attachments/assets/fa353dcc-c810-42c3-bcf0-f3447253066c)

  * 다이어그램 메타 테이블 매핑 시 외래키를 이용한 복합키의 Join 조건을 설정시, FetchType.LAZY를 사용하여 연관된 엔티티가 실제로 필요할 때만 로딩되도록 구현함. 이를 통해 불필요한 DB 접근을 줄이고 메모리 사용을 최적화할 수 있었음. N+1 문제가 발생할 수 있지만, 다이어그램 메타 테이블은 사용자가 작성하고 저장한 다이어그램 목록을 보여주는 용도로 사용되며, 외래키가 참조하는 다이어그램 데이터 테이블보다 사용 빈도와 데이터 양이 많았음. 따라서 N+1 문제를 감안하더라도 FetchType.LAZY 설정이 더 합리적이라고 판단함.
 
  * JPA를 사용하여 CRUD를 구현시 기본적으론 JPA의 쿼리 메서드를 활용하여 구현하였고, 복잡한 쿼리나 UPDATE, DELETE, INSERT와 같은 수정 작업이 필요한 경우 @Modifying을 사용하여 커스텀 쿼리를 사용하여 구현함.
----
*  실질적인 다이어그램 데이터 검사 구현

    * Json Schema와 json-schema-validator를 사용하여 사용자가 서버로 보내는 다이어그램 데이터가 적절한 구조와 값을 가지고 있는지 검증하는 기능을 구현.

    * 다이어그램 데이터는, 다이어그램을 정확하게 그릴 수 있어야 하기 때문에, 올바른 순서와 값으로 저장되어야 함. 따라서 Json Schema를 통해 저장 전에 미리 검증하여 데이터 무결성을 보장함.
----
* 클라이언트에서 다이어그램 작성 구현

  * useRef를 활용해 canvas DOM 요소를 참조하여, 사용자가 브라우저 상에서 직접 다이어그램을 작성하고 수정할 수 있도록 구현함.
 
  * 다이어그램은 각각 canvas에서 X, Y 좌표에 따라 그려지므로, 작성 순서에 상관없이 위치 정보를 바탕으로 항상 사용자가 그린대로 정확하게 렌더링되도록 구현함.
 
  * 다양한 기능에 맞게 다이어그램을 그리기 위해 다이어그램의 데이터를 구조화하고 [diagram, setDiagram] = useState<DiagramComponent[]>([]); 형태로 다이어그램들을 관리하여, 기능적용과 수정, 삭제, 삽입을 원활하게 진행하도록 구성함.
 
  * **DiagramComponent 구조**
 
  ```
  interface DiagramComponent {
  id: number;
  x: number;
  y: number;
  width: number;
  height: number;
  name: string;
  highValue: number;
  lowValue: number | null;
  color: string;
  zIndex: number;
  type: 'Organic' | 'Metal' | 'Other';
  cuts: { start: number; end: number }[];
  showValues: boolean;
  invert: boolean;
  }
----
* 다이어그램 저장 예외처리 구현

  * 서버 오류 등으로 인해 정상적인 저장이 불가능하거나, 사용자가 저장하지 않고 작성 페이지를 이탈한 경우를 대비해, 다이어그램 데이터를 JSON 문자열 형태로 Local Storage에 임시 저장하는 기능을 구현.
 
  * 사용자가 작성한 다이어그램 목록 페이지에서 임시 저장된 항목도 함께 출력되도록 하여 언제든지 수정 및 저장이 가능하도록 구현.
 
  * Local Storage에 임시저장될 데이터의 구조
 
  ```
  const data = {
        uuid : nowUuid,
        diagram : JSON.stringify(nowDiagram.current),
        createDate : date
      };

      localStorage.setItem(nowUuid, JSON.stringify(data));
----
* 실제 서비스를 위한 서버 환경 구축/배포

  * AWS EC2 (Ubuntu 24.04.1)을 생성하고 기본적인 보안규칙 (인바운드 : 3306, 80, 22, 443)을 설정하여 클라우드 서버 배포환경 구축.
 
  * Nginx를 리버스 프록시 서버로 설정하여 클라이언트와 서버 간 직접 연결을 차단하고, 포트노출을 최소화 하여 기본적인 보안체계 구축.
 
  *  Let's Encrypt를 통해 무료 SSL 인증서를 적용하여 HTTPS 기반의 보안 통신 환경을 구성.
 
  *  Spring Boot 서버를 Docker 이미지화한 후, 배포 서버에 Nginx, Certbot, Spring Boot 서버, MySQL을 각각 Docker 이미지로 구성하고, Docker Compose 설정 파일을 작성하여 실행 순서와 환경설정을 정의한 뒤, 전체 서비스를 Compose로 자동 배포되도록 구축.
 
  *  로컬 PC에서 작업한 MySQL 데이터를 Dump 파일로 추출한 후, Docker Compose 설정 시 해당 파일을 활용해 초기화하도록 구성하였으며, 데이터의 영속성을 위해 볼륨을 설정.

  *  도메인 구매 후, AWS Route 53을 통해 DNS, 네임서버 설정을 구성하고, 배포 서버에 적용하여 외부 접근 시 IP가 아닌 도메인으로 접속 가능하도록 구성.
 
  *  Docker Compose 설정


  ```
  services:
  nginx:
    image: nginx:latest
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
      - ./certs/conf:/etc/letsencrypt
      - ./certs/www:/var/www/certbot
    ports:
      - "80:80"
      - "443:443"
      # 6시간마다 Nginx 설정을 다시 불러오도록 자동 재로드하며, Nginx를 포그라운드에서 실행, 뭔가 업데이트됐을지도 모르니까 그냥 6시간 마다 reload하자
    command: "/bin/sh -c 'while :; do sleep 6h & wait $${!}; nginx -s reload; done & nginx -g \"daemon off;\"'"  
    depends_on:
      - springboot   # springBoot 실행중이어야 실행한다

  certbot:
    image: certbot/certbot:latest
    volumes:
      - ./certs/conf:/etc/letsencrypt
      - ./certs/www:/var/www/certbot
      # Certbot으로 SSL 인증서를 12시간마다 자동 갱신 시도, 갱신 성공후 Nginx를 재시작하는 무한 루프
    entrypoint: "/bin/sh -c 'trap exit TERM; while :; do certbot renew && nginx -s reload; sleep 12h; done;'" 

  mysql:
    image: mysql:8.0.30
    environment:
      MYSQL_ROOT_PASSWORD: ***
      MYSQL_DATABASE: diagram
      MYSQL_USER: admin
      MYSQL_PASSWORD: ***
      TZ: Asia/Seoul
    command:
    # 클라이언트가 어떤 문자셋을 지정하든 무시하고 character_set_server로 설정된 문자셋만 사용, 설정 안하면 한글이 깨져버림
      - --skip-character-set-client-handshake 
    volumes:
      - mysql_data:/var/lib/mysql
      - ./db_dump.sql:/docker-entrypoint-initdb.d/dump.sql  # dump.sql을 사용해서 DB 초기화
    ports:
      - "***:***"

  springboot:
    image: ***/drawd-1.3.1-snapshot:v1.3.1
    ports:
      - "***:***"
    depends_on:
      - mysql   # Mysql 실행중이어야 실행 한다

  volumes:
    mysql_data: {}  # 볼륨을 기본설정으로 생성 
<br>

### Trouble Shooting

----

* 문제 상황
  
  클라이언트에서 재료 검색 기능 사용 시, 사용자의 모든 텍스트 입력마다 서버 요청 함수가 실행되어, 최악의 경우 영어 기준 15자 입력에 15번의 요청, 한국어는 그 이상의 요청이 발생해 서버에 과도한 부담이 발생.

* 해결 방법

  해결 방법을 탐색하는 과정에서 Throttling과 Debouncing 기법에 대해 알게 됨.

  Throttling은 일정 시간 간격 내에 발생하는 여러 이벤트 중 주로 첫 번째 이벤트만 처리하고, 이후 이벤트는 무시하는 방식. 이 방식은 일정 주기로 이벤트를 처리하기 때문에, 입력이 계속되는 상황에서는 최악의 경우 최소 2번 이상의 서버 요청이 발생하거나, 정상적인 요청이 진행될 수 없다고 판단함.

  반면, Debouncing은 마지막 이벤트 발생 후 일정 시간이 지나도 추가 입력이 없을 경우에만 이벤트를 처리하는 방식. 즉, 사용자가 입력을 멈춘 시점을 기준으로 서버 요청이 발생하므로, 불필요한 요청을 최소화할 수 있다고 판단함.

  재료 검색 기능은 사용자가 타이핑을 완료한 이후에 검색 요청이 발생하는 것이 가장 적절하다 생각하여, Throttling보다 Debouncing이 더 적절하다고 판단함. 따라서 Debouncing을 적용하여, 사용자의 입력마다 서버 요청이 발생하던 기존 방식보다 서버 부하를 줄이고, 효율적인 요청 처리를 구현함.
  <br>
----

* 문제 상황

  프로젝트 배포 시, Frontend 서버에는 도메인을 적용했지만 Backend 서버는 IP 주소로 직접 접근하도록 설정하여 배포함. 이 상태에서 Backend 서버가 JWT를 발급한 뒤 Cookie로 클라이언트에 전달하였으나, 클라이언트 측에 Cookie가 저장되지 않는 문제가 발생.

* 해결 방법

  문제 파악 중, 클라이언트와 서버의 도메인이 달라 CORS 정책으로 인해 쿠키가 저장되지 않는다고 판단함.

  따라서 Spring Boot 서버에 Access-Control-Allow-Origin과 Access-Control-Allow-Credentials 설정을 적용했지만, 여전히 클라이언트에 쿠키가 저장되지 않았음.

  문제를 계속 탐색하던 중, 쿠키는 기본적으로 동일한 도메인 간에만 교환이 가능하다는 점을 확인함.

  즉, 도메인을 명시하지 않은 쿠키는 다른 도메인에서 접근할 수 없으며, 쿠키 자체에도 Domain 속성을 설정해야 한다는 점을 알게됨.

  그래서, 발급받은 도메인을 기반으로 서브 도메인을 생성하고, Frontend 서버에는 서브 도메인, Backend 서버에는 메인 도메인을 적용하였고, 쿠키 생성 시 도메인을 명시하여 쿠키가 공유될 수 있도록 구성함.

  그 결과, 쿠키는 정상적으로 클라이언트에 저장되었고, 서버와의 인증 흐름도 원활히 작동함.
  <br>
----

### 참고

* 이 프로젝트는 실제로 서비스 중 입니다. https://do.drawd.store/

* 해당 프로젝트는 이후 Java Swing 기반의 데스크탑 버전으로 기능을 추가/보완하여 확장하였습니다. [DrawD Desktop GitHub](https://github.com/yangsp31/OLED-Diagram-DrawD_3.0)

* 프로젝트 GitHub

  * [DrawD Next.js GitHub](https://github.com/yangsp31/DrawD_Next.js)
 
  * SpringBoot 깃허브는 아직 서비스 중이기에 제출하지 않았음.
<br><br><br><br>

## ReLife - 이미지 생성형 A.I와 이미지 처리를 활용한 인테리어 시뮬레이션 서비스<br><br>(2024.03.05. ~ 2024.06.02.) (4인, 팀 프로젝트)

### 개요

사용자로부터 방 이미지를 입력받아, 이미지 생성형 A.I를 활용해 원하는 색상, 테마, 공간 유형으로 변환된 인테리어 이미지를 제공합니다.

또한, 여러 장의 이미지를 이어붙여 파노라마 이미지를 생성 후, 이를 바탕으로 360도 VR 뷰를 제공함으로써 사용자에게 간접적이지만 공간감을 느낄수 있도록 제공하는 인테리어 시뮬레이션 서비스 입니다.
<br><br>

### Architecture

![Architecture1](https://github.com/user-attachments/assets/430e87fd-4b91-4f0f-9245-1c03849b6522)
<br><br>

![ReLife Flow](https://github.com/user-attachments/assets/b0fe7b70-fecf-474d-a90d-1a8adddcb1c9)
<br><br>

### 사용기술

* Next.js (Three.js)
* Redis
* Flask (OpenCV)
* AWS (EC2, S3, NginX)
* 외부 API (인테리어 이미지 변환 A.I서비스 REimagineHome API) https://www.reimaginehome.ai/
<br>

### 개발내역

* Next.js API Route 로직 중 단일 이미지 처리 로직 구현

  * 사용자가 업로드한 단일 이미지를 AWS S3에 업로드, ${cookie}/short/${file.name}구조로 이미지 저장후 이미지 URL 반환 구현.
 
  * 외부 이미지 생성형 AI 서비스(reimagineHome API)에 반환된 이미지 URL을 포함한 마스크 생성 요청 구현.
 
  * 마스크 생성 요청 성공 시, Redis(Vercel KV)를 사용해 작업 식별자(Job ID)와 Cookie에 담긴 사용자 식별코드, 프롬프트, 테마, 색깔등의 사용자 작업 정보 저장 구현.
----
* Next.js API Route 로직 중 다중 이미지(파노라마) 처리 로직 구현

  * 사용자가 업로드한 3장의 이미지를 AWS S3에 업로드, ${cookie}/panorama/piece/${file.name} 구조로 이미지 저장후 3장의 이미지 URL을 담은 배열 반환 구현.
 
  * Flask 서버에 3장의 이미지 URL이 담긴 배열을 포함한 파노라마 이미지를 생성 요청 구현.
 
  * 외부 이미지 생성형 AI 서비스(reimagineHome API)에 반환된 파노라마 이미지 URL을 포함한 마스크 생성 요청 구현.
 
  * 마스크 생성 요청 성공 시, Redis(Vercel KV)를 사용해 작업 식별자(Job ID)와 Cookie에 담긴 사용자 식별코드, 프롬프트, 테마, 공간 타입 등의 사용자 작업 정보 저장 구현.
----
* 마스크 이미지 응답 처리 웹훅 구현

  * 마스크 이미지 생성 완료시 반환되는 Job ID를 기반으로 Redis(Vercel KV)에서 작업을 등록한 사용자의 식별 코드를 탐색 후, 사용자의 작업 정보에 마스크 이미지 URL을 저장하도록 구현함.
 
  * 반환된 마스크 이미지 URL을 기반으로 최종 이미지 생성 요청을 전송하고, 이미지 생성 요청 성공 시 반환되는 새로운 Job ID를 키로 사용해 사용자 식별 코드와 함께 Redis(Vercel KV)에 저장.
----
* 최종 이미지 응답 처리 웹훅 구현 & 클라이언트에게 반환

  * 반환된 최종 이미지 URL을 함께 반환된 Job Id를 통해 요청 사용자를 Redis(Vercel KV)에서 탐색한 후, 사용자 작업 정보에 저장.
 
  * 만일 최종 이미지가 Panorama 타입의 요청일 경우 Flask 서버로 왜곡 요청 진행.
 
  * 클라이언트가 주기적으로 결과를 조회하기 위해 Polling방식으로 주기적 요청을 보내면, 서버는 요청에 포함된 쿠키의 사용자 식별 코드를 활용하여 Redis(Vercel KV)에서 해당 사용자에 대한 최종 이미지 URL을 탐색하고, 존재 시 응답으로 반환함.
----
* Redis(Vercel KV)를 사용한 CRUD 구현

  * JSON과 비슷하게 키 하나에 여러 필드를 담을 수 있는 Redis Hash를 사용해, 데이터를 구조화 하여 관리하고, 필드 단위로 쉽게 수정할 수 있도록 구성함.
  <br>
 
  ```
  Redis(Vercel KV)에서 Job Id와 사용자 식별 코드 구조
  
  {jobId} : {
      cookie : {cookie},
      type : {type}
  }
  
  Redis(Vercel KV)에서 사용자 별로 관리되는 작업 정보

  {cookie} : {
      prompt : {prompt},
      spaceType : {spaceType},
      designType : {designType},
      maskUrl : [{maskUrl}],
      generateUrl : {generateUrl}
  }

----
* 파노라마 이미지 생성 구현

  * 유저가 업로드하여 AWS S3에 저장된 3장의 이미지 URL을 포함한 Panorama 이미지 생성 요청이 Flask로 들어올 경우, 특징점 검출, 특징점 매칭, 호모그래피 추정, 이미지 왜곡 및 구형 매핑, 블랜딩 순서로 진행되는 이미지 스티칭 기술을 OpenCV에서 제공하는 cv2.Stitcher을 사용하여 진행함.
 
  * 생성된 파노라마 이미지의 가로 길이를 외부 API 서비스의 최대 허용범위까지 늘린 후, 360도 VR뷰로 출력시 이미지가 반전되는 상황을 대비하여 이미지 좌우반전을 진행.
 
  * 파노라마 이미지 생성 후, 결과 이미지를 AWS S3에 업로드하여 직접적인 이미지 데이터 전달 없이 URL을 통해 접근 가능하도록 구현.
 
  * 서버는 이미지 자체가 아닌 URL만 반환하여, 응답 크기를 줄이고, 서버 리소스 사용을 최소화하는 방식으로 이미지 전달을 구현.
----
* 이미지에 왜곡 적용 구현

  * 외부 API를 통해 생성된 파노라마 이미지에, 극좌표(r, θ)를 활용한 비선형 함수 기반의 거리 조절 기법을 적용하여 중심부는 덜 왜곡되고 외곽은 더 강하게 왜곡되는 배럴 왜곡 효과를 구현.
 
  * 이미지 왜곡 과정에서 가장자리 픽셀이 심하게 일그러지거나 잘려나가는 문제를 방지하기 위해, 왜곡된 이미지의 중심을 기준으로 일정 비율로 확대 후, 이미지의 4변에 검은 여백을 추가하여 왜곡된 이미지를 최대한 반듯하게 유지.
 
  * 최종 왜곡 이미지 생성 후, 결과 이미지를 AWS S3에 업로드하여 직접적인 이미지 데이터 전달 없이 URL을 통해 접근 가능하도록 구현.
 
  * 이미지 스티칭 예시자료
 
  ![image](https://github.com/user-attachments/assets/12436547-36d2-4d0a-aa53-23c7a3902a45)
<br>

### Trouble Shooting

----

* 문제 상황

  외부 API를 통해 이미지 변환을 마친 파노라마 이미지를 360도 VR 뷰로 출력하기 위해, 투명한 구에 매핑하는 방식을 사용했음.

  하지만 사용자는 구의 내부에서 이미지를 바라보는 구조이기 때문에, 핀쿠션 왜곡(오목 렌즈 효과)이 발생하여 이미지가 비정상적으로 뒤틀리는 문제가 발생함.

* 해결 방법

  이미지를 360 VR뷰로 출력하는 환경은 투명한 구 위에 이미지를 매핑하는 것이며, 사용자는 구의 내부에서 이미지를 바라보는 상황임.

  따라서, 이미지에 극좌표(r, θ)를 활용한 비선형 함수 기반의 거리 조절 기법을 적용하여 중심부는 덜 왜곡되고 외곽은 더 강하게 왜곡되는 배럴 왜곡(볼록 렌즈 효과)을 적용한다면, 완벽하게는 아니여도 유의미 하게 핀쿠션 왜곡(오목 렌즈 효과)을 상쇄할 수 있다고 판단함.

* 예시자료
 
  * 배럴 왜곡(볼록 렌즈 효과) 전
  
  ![image](https://github.com/user-attachments/assets/fa70daec-b363-468b-8bd1-e266b209dab0)
  <br><br>

  * 배럴 왜곡(볼록 렌즈 효과) 후

  ![image](https://github.com/user-attachments/assets/989eadc6-2b1d-4715-8f30-327c37cb7dfd)
  <br><br>

  완벽하게 핀쿠션 왜곡(오목 렌즈 효과)을 상쇄하지는 못하였어도 효과는 있었다.
  
----

### 참고

* 이 프로젝트는 대학교 졸업작품으로 진행된 프로젝트 이다.

* 해당 프로젝트를 주제로 논문 작성 결과, 2024년 한국디지털콘텐츠학회 하계종합학술대회 대학생 논문경진대회 발표논문 중 동상 논문으로 선정 되었다.

* 프로젝트 GitHub

  * [ReLife Next.js GitHub](https://github.com/yangsp31/ReLife-Next.js)
 
  * [ReLife Image Processing Server GitHub](https://github.com/yangsp31/Image_Processing_Server)
<br><br><br>

# 학력

### 선문대학교 컴퓨터공학부 컴퓨터공학과 학사 (2019.03. - 2025.08.예정)

### 안화고등학교 (2016.03. - 2018.02.)
<br><br>

# 수상 내역

### 동상 - 2024년 한국디지털콘텐츠학회 하계종합학술대회 대학생 논문경진대회
<br><br><br>

# 읽어주셔서 감사합니다.

* 포트폴리오에서 미처 다 말하지 못한 부분은 GitHub와 기술 블로그에 있으니 필요하시면 방문해 주세요.

  * GitHub : https://github.com/yangsp31
 
  * 기술 블로그 : https://velog.io/@yang_seongp31/series



 
  

  











  






