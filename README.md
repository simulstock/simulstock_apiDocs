# SimulStock

<br>

<img src="https://github.com/simulstock/simulstock_docs/blob/main/logoImage.jpg?raw=true">

<br>


## 서비스 목적

#### 1) 보유 주식 관리

증권 계좌별로 '장기 투자', '단기 투자' 등 목적을 다르게 운용하는 사람들이 많다. 

내가 보유한 모든 주식에 대해 한눈에 볼 수 있고, 다양한 정보를 통해 쉽게 관리할 수 있는 서비스를 만든다.

> 우선, 사용자가 직접 구매한 주식을 입력하여 관리하는 방식으로 진행한다.

<br>

#### 2) 가상 모의 투자

주식을 처음 시작하는 사람들이 연습해보거나 관심을 가질 수 있도록 한다.

회원 가입 완료 시 초기 자산 부여(1억원) 후, 가상으로 주식을 구매해보는 서비스를 만든다.

현재 전체 유저의 자산 랭킹 (보유 주식 + 자산), 많이 산 주식 종목, 분야 등 다양한 지표를 제공해준다.

> 실제 주식처럼 실시간으로 진행하기엔 자원 및 비용 문제가 있다.
>
> 종가 기준으로 모의 투자를 진행하여, 16:00 - 08:00에 매수, 매도가 가능하도록 설정한다.

<br>

## 기술 스택

- Frontend : ReactJS
- Backend : Spring Boot, Spring Data JPA, MariaDB
- DevOps : AWS EC2, AWS RDS, Travis CI, CodeDeploy

<br>

## 프로젝트 기능 정리

1. #### 유저 관리

   - 회원가입 및 로그인
     - id, email, password, nickname, asset, stock_ role
   - 회원정보 수정
   - 회원 탈퇴
   - 로그인 유지
   - +소셜 로그인(구글, 네이버, 카카오 등)

2. #### 데이터 관리

   - 주식 상장 리스트 저장
     - code, name, price, sector
   - 하루 주기 종가 업데이트 자동화 스크립트 개발
     - code, openPrice, closePrice, highPrice, lowPrice

3. #### 포트폴리오 관리(REST API)

   - 주식 INSERT / UPDATE / DELETE / SELECT
     - code, buyPrice, period(단기,장기)
   - 종가 기준 가격 대비 수익률 관리
     - period별, sector별 등등 chart 화

4. #### 모의투자 관리(REST API)

   - 주식 매수/매도
     - user_id, code, buyPrice, amount, status : 해당 code 주식 buyPrice * amount - (tax+fees)
   - 매수 시 자산 부족 체크
   - 유저 별 자산(asset + 보유 주식) 랭킹


