## 프로젝트명
클라우드기반 지하철 시간 검색 서비스


## 프로젝트 멤버 및 담당파트
### 조재우(1인 팀)
수행작업 : 웹서버 구축,모듈 구현 및 통합, HTML작성 및 연동과 렌더, 코드 경량화, 클라우드상에 서비스 업로드(git hub이용)


## 프로젝트 소개 및 개발 내용 소개
이 프로젝트를 통해 개발하고자 한 것은 웹을 이용해 일종의 편의 기능을 제공하는 소프트웨어이다.
이 웹 서비스는 지하철역명을 입력하는 것 만으로 해당역의 첫차부터 막차까지의 출발시간을 제공하는 서비스이다.

요일마다 그리고 특정 사유로 바뀔 수 있는 전철 출발시간에 대한 데이터를 직접 수집하기 힘들다. 
또한 클라우드 특성상 자료 용량의 증가 >> 비용 증가로 이어지므로 실시간 요청을 통해 전철 시간에 대한 데이터를 얻을 수 있는 공공데이터의 오픈 api 서비스를 사용하였다.

>공공데이터 오픈 api를 사용하기위한 해당 국가 기관의 허가가 필요했다. >> 신청을 통해 허가를 받았다.

>파이썬3에 flask를 import하여 웹서버를 구현하였다.

>웹에서의 사용자의 입력값에 따라 api를 call하기 위한 모듈을 구현하였다.

>call한 api는 xml포맷으로 request를 받게 되는데 xml 문자열을 바로 웹에 띄우면 유저의 가독성이 떨어지므로 파싱 모듈을 구현하였다.

>처리된 가독성이 좋아진 결과물을 웹서버 상에서 html 파일 렌더링시에 data를 넘겨서 작성되도록 구성하였다.

>모듈의 코드를 경량화 하고 api를 call하는 모듈과 파싱하는 모듈을 통합하였다.

>추가 서비스 기능 업데이트나 활용이 쉽게 구성되었다. ex)문자열 list를 만들어주는 함수에 boto3 패키지를 임포트하여 해당 문자를 읽어서 음성 스트림으로 반환해주는 aws 클라우드의 기능을 추가할 수 있다. (경량화와 활용성은 프로젝트 시작부터의 목표중 하나였다.)


## 프로젝트 개발 결과물
![mydiagram](https://user-images.githubusercontent.com/74773343/101609340-353b4600-3a4a-11eb-93a9-4a1ebde81317.PNG)


## 개발 결과물 사용 방법

## 개발 결과물의 필요성 및 활용방안
