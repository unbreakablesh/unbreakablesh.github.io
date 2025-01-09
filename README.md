#  ⛽ Stop scan

## 프로젝트 소개 
고속도로를 이용하는 운전자들을 위해 다양한 고속도로 휴게소, 주유소, 전기차 충전소 정보를 제공하는 웹 애플리케이션<br>
실시간 정보, 주변 편의시설, 관광 명소 등을 한눈에 확인할 수 있다.l

## 프로젝트 팀 
- **엄현빈** - 프로젝트 관리,데이터수집,백엔드 개발,UI디자인 
- **이재우** - 프론트엔드 개발,게시판기능,백엔드 개발
- **위지은** - 프론트엔드 개발,차트와 챗봇관련 백엔드 개발
- **조수호** - 챗봇개발,프론트엔드 개발


## 기능
- 고속도로별 휴게소 정보 조회 
- 휴게소 상세 정보 및 편의시설 확인
- 지도 기반 휴게소 위치확인
- 주변 주유소 및 충전소 실시간 상태확인 
- 제주도 관광명소,제주도 충전소 실시간 상태확인
- 음성인식 기능을 통한 정보제공 챗봇
- 실시간 유가차트 확인 
- 상호로 주유소 주소,공급업체 검색
- 로그인,회원가입

### 로그인

![login](https://github.com/UHB4/rest_area/assets/153577215/1c98cea5-7f34-4ef7-9517-b95b8552f91c)

### 회원가입 

![register](https://github.com/UHB4/rest_area/assets/153577215/d18978e1-6b41-4b70-8887-d0c83be14593)

### 프로필 사진업로드

![profileUpdate](https://github.com/UHB4/rest_area/assets/153577215/ea068e9e-9d5c-401f-8542-6c465dffaf9b)

### 주유소 찾기 
![findFuel (2)](https://github.com/UHB4/rest_area/assets/153577215/56906741-0d6f-41ea-bf36-ac40437fd0f6)

### 연료별 찾기
![findFuelType](https://github.com/UHB4/rest_area/assets/153577215/53eb70cf-f2f6-412a-baea-13677c235cfa)

### 휴게소 찾기

![image](./readmeImg/메인화면검색.png)

사용자가 원하는 도로를 선택할 수 있는 드롭다운 메뉴 제공.
사용자가 도로를 선택하고 "검색" 버튼을 클릭하면, 선택된 도로에 해당하는 휴게소 페이지(/restarea/${selectedRoute})로 네비게이션   

![image](./readmeImg/동해.png)

넘어온 URL 에서 도로 이름 추출하고 해당 도로에 있는 휴게소 정보를 서버에서 가져옴
axios를 사용하여 휴게소정보외에도 브랜드,연료가격,시설,인기음식 등에 대한 추가데이터를 비동기적으로 가져옴.   


### 제주관광안내
![image](./readmeImg/제주관광.png)

카테고리별 선택, 태그별 선택으로 관광지 정보제공

### 제주 전기차충전소찾기
![image](./readmeImg/제주전기차충전소.png)


![image](./readmeImg/제주전기차충전소.png)

제주도 전기차 충전소 상태 제공

![image](./readmeImg/통계.png)
#### * 검색
전국 주유소,충전소의 상호명으로 주소와 공급업체 확인 가능
#### * 실시간 차트
| 전국 주유소 평균가격     | 내 주변 주유소,충전소 가격 |
  |---|---|
|전반적인 상품별 가격 확인    | 가격순 (색상,크기로 확인) |


|최근 7일간 전국 일일 평균가격 | 내 주변 전기차 충전소명 |
  |---|---|
|상품별 가격 추세 확인   |(슬롯수 제공업체가 많다는 가정)

![Animation](./readmeImg/chatbot2.gif)
![image](./readmeImg/chat4.png)

#### 챗봇
Geolocation 함수를 이용하여 실시간 사용자의 위치를 기반으로 가장 가까운 주유소 가격 정보와 전기차 충전소의 위치 정보를 제공.
XML 형식으로 된 주유소 데이터와 SQL 오라클 DB에 넣어놓은 전기차 충전소 데이터를 각각 불러오는 방식이 달랐지만, Flask 서버를 이용하여 문제없이 불러옴.
STT와 TTS 기능을 추가하여 챗봇을 고도화함. 음성인식 기능을 추가하여 사용자가 음성으로 키워드를 입력하면 그에 맞는 데이터를 불러와 채팅 메시지로 정보를 표시하고(TTS), 메시지를 읽어주는 기능을 구현함(STT).
우리 사이트의 주요 페이지를 간편하게 바로 들어갈 수 있도록 버튼을 누르면 채팅 메시지로 링크가 표시되도록 구현함.
GPT-4의 기능을 추가하여 사용자의 구체적인 요구사항을 들어줄 수 있음.



![image](./readmeImg/충전소코드.png)
![Animation](https://s5.ezgif.com/tmp/ezgif-5-251fbdb3f4.gif)


사용자의 현재 위치를 받고 그위치로 서버에다 요청을하고
주변의 주유소및 충전소 데이터를 받아옴.



![image](./readmeImg/충전소서버코드.png)


파이썬으로 api를 요청해 적재한 30만개의 충전소 정보 데이터와
실시간으로 서버에서 요청한 충전소 상태 api의 statid를 매칭해 일치하는 데이터만 맵과 리스트의
표시











# 개발 환경
- intellij 
- pycharm
- sql developer
- putty
- win SCP


## Main Stack

<img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=Flask&logoColor=white">
<img src="https://img.shields.io/badge/Redux-764ABC?style=for-the-badge&logo=Redux&logoColor=white"> 
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white">
<img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=Node.js&logoColor=white">
<img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=React&logoColor=white">
<img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=CSS3&logoColor=white">
<img src="https://img.shields.io/badge/OracleDB-F80000?style=for-the-badge&logo=oracle&logoColor=white">
<img src="https://img.shields.io/badge/Amazon%20EC2-FF9900?style=for-the-badge&logo=Amazon%20EC2&logoColor=white">



## Main Library

### Redux & Redux-persist

- 전역 상태 유지
- redux-persist를 사용하여 redux의 state 저장소를 local storage로 사용
- ex)사용자가 response로 받아오는 jwt 정보를 local storage에 저장
  ![image](./readmeImg/localStorage.PNG)

### axios
- HTTP request & respose

### Material UI

- CSS 프레임워크
- 로그인과 회원가입에 사용

### react-router-dom v6

- 라우팅, 동적 라우팅, query parmeter와 uri parameter를 효율적으로 파싱

### jsonwebtoken

- jwt 생성 및 검증
- 서버에서 액세스 토큰과 리프레시 토큰을 생성하고 검증하는데 사용

### bcrypt 

- 비밀번호 해시화 및 비교
- 사용자의 비밀번호를 데이터베이스 저장하기 전에 해시화 

### OracleDB

- Oracle 데이터베이스와의 연결 및 쿼리 실행
- 'oracledb'라이브러리를 사용하여 Oracle 데이터베이스와 상호작용

### Kakao Maps SDK

- 카카오 지도 API를 이용하여 지도를 표시하고,마커,오버레이, 원형등을 추가


## 배포구조
![image](./readmeImg/구조.PNG)   
* #### `aws`에 배포시 구조입니다



## 프로젝트 관리 

![image](./readmeImg/1.png)   
각 서버를 효율적으로 관리하기 위해, React, Express, 그리고 Flask를 사용하는 세 개의 서버에 각각 원격 레포지토리를 생성   
https://github.com/UHB4/rest_area_flask   
https://github.com/UHB4/rest_area_express

   
![image](./readmeImg/2.png)   
각자가 자신의 브랜치를 만들어 작업하고, 마스터 브랜치에 업데이트하는 방식으로 작업을 진행

![image](./readmeImg/3.png)





   








