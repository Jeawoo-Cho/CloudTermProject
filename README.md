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

위 그림과 같이 작동하는 결과물을 구현하는데 성공하였다.

>유저는 aws 클라우드의 해당 서비스가 구동되고 있는 인스턴스의 주소(특정포트)로 접속한다.

>요청을 기다리던 Webmodule이 요청에 대한 응답으로 flask에서 templates 폴더의 myname.html 화면을 웹으로 띄워준다.

>여기서 입력한 정보를 다시 Webmodule로 가져가서 import되어있는 api_call + xml파싱 모듈에서 공공데이터서버에 api를 요청한다.

>api 요청을 통해 받은 xml데이터를 api_call + xml파싱모듈 에서 가공한다.

>가공된 데이터를 이용하여 Webmodule이 templates폴더의 search.html에 추가 내용을 작성한다.

>해당 html을 유저의 웹으로 띄워준다.

## 개발 결과물 사용 방법
![Sim1](https://user-images.githubusercontent.com/74773343/101612889-7d5c6780-3a4e-11eb-837a-9b5491e10b6c.PNG)

처음 접속하면 위 그림과 같은 웹 화면을 볼 수 있다.
텍스트 상자에 역이름을 입력하고 요일과 상하행 중에 어떤것을 검색할지 선택한 뒤에 "시간표검색"을 누른다.


![Sim2](https://user-images.githubusercontent.com/74773343/101612902-81888500-3a4e-11eb-924e-b5689a3e9fba.PNG)

위 그림은 평내호평의 시간표를 출력해본 결과이다.


![Simul01](https://user-images.githubusercontent.com/74773343/101614794-b85f9a80-3a50-11eb-9381-6c610980c306.PNG)

![Simul02](https://user-images.githubusercontent.com/74773343/101614803-bac1f480-3a50-11eb-8163-5a8c5e1a7a5d.PNG)

![cloud01](https://user-images.githubusercontent.com/74773343/101614816-bd244e80-3a50-11eb-89b9-95f9e05d38bf.PNG)

클라우드로 서비스를 이관하고 접속하여도 잘 작동한다.

마지막은 가상머신에 ssh로 접속하여 서비스를 수행중인 터미널 창의 모습이다.

## 개발 결과물의 필요성 및 활용방안
당연하게도 
