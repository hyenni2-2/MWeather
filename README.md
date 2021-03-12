# Team MayWeather : Weather Wear 


## BITCAMP 최종 프로젝트 WeatherWear : Closet 게시판 구현 (BITCAMP Final Project - Designing Closet Board)

### 사용기술 ( Technologies) : Java, Spring Framework, Javascript, Jquery, SPA(Single Page Application), MSA(Micro Service Architecture) 

### 1. Purpose ; 기획의도 
##### 사용자가 자유롭게 Drag & Drop 기능을 이용하여 원하는 코디 조합을 할 수 있도록 구현하였다. 
##### User can easily use drag & drop function. and with that images, user can posts text on Closet board.  
<img src="https://user-images.githubusercontent.com/71998026/110907553-eb1b7680-8350-11eb-9057-72a014e7bbf0.png">


### 2. Codes ; 구현기능
##### Drag & Drop  
<img src="https://user-images.githubusercontent.com/71998026/110911461-19e81b80-8356-11eb-841a-83125640d9b1.png">
<img src="https://user-images.githubusercontent.com/71998026/110908634-72b5b500-8352-11eb-8aaa-67c9d456c0c1.gif">  


#### Basic Board(Using Spring Framework) : CRUD(Create, Read, Update, Delete)
#### Create ; 글쓰기 
드래그한 이미지를 그대로 글쓰기 메뉴에서 출력하였다. (Dragged images are keeping their position, can be submitted to Closet board with texts.)
![메이웨더 PPT 설명 pptx의 사본 (2)](https://user-images.githubusercontent.com/71998026/110911634-4c921400-8356-11eb-925a-cb0d38f05a5b.png)

#### Read ; 리스트
유저가 등록한 게시글을 최신순으로 노출하였다. 또한, 좋아요 기능을 추가하였다. (Postings are listed by latest date and adding like function, user can count their own like.)
![메이웨더 PPT 설명 pptx의 사본 (4)](https://user-images.githubusercontent.com/71998026/110912674-8fa0b700-8357-11eb-96ae-6fa2d54cb070.png)

#### Update/Delete ; 수정/삭제
본인이 등록한 게시글을 수정 & 삭제할 수 있도록 하였다. 
(User can edit & delete their own post, which is confirmed same user through login process.)
<img src="https://user-images.githubusercontent.com/71998026/110913082-08a00e80-8358-11eb-9fed-33ecdead9f0d.png">
<img src="https://user-images.githubusercontent.com/71998026/110913129-15246700-8358-11eb-891d-88050f830b2b.png">
<img src="https://user-images.githubusercontent.com/71998026/110913163-21102900-8358-11eb-81d5-1e12b757344e.png">


#### 3. Review ; 느낀 점
##### 1) Jquery Draggable UI 
처음엔 Jquery Draggable UI를 사용하지 않고 HTML5 기본 API인 Drag & Drop 기능을 이용하여 구현하려 했으나, Jquery Draggable UI를 이용하여 구현하는 편이 더 간단하여 Jquery UI로 구현하였다.
그러나 프로젝트 기획의도인 모바일 웹에서는 draggable이 되지 않는다는 치명적인 단점이 있었고, 이를 jquery.ui.touch.js(https://github.com/furf/jquery-ui-touch-punch)를 이용하여 해결하였다.

그리고, 처음 리스트를 구상하였을 때는 드래그한 이미지들을 리스트 화면에 출력할 의도였지만, 어느정도 프로젝트가 진행된 뒤 리스트 구현 단계에서 다시 확인해보니 이미지 출력을 위해서는 코디 화면에서 드롭한 이미지가 위치한 가로/세로의 길이(기준점으로부터), x,y,z 좌표를 고려하여 리스트 구현 시 어느 정도 줄어든 배율로 하여 정확히 같은 위치에 구현시켜야 하는지 계산하였어야 했으나, 그 부분을 고려하지 못하고 만들어 리스트 화면에 이미지가 아닌 유저가 작성한 텍스트가 뜨게 되었다. 이 부분을 첫 기획 단계에서 고려하지 못한 점이 매우 아쉬운 점이다. 


##### 2) CRUD 기능
게시판을 혼자 힘으로 구현해보는 것이 처음이었기 때문에, MVC Model과 Spring Framework에 대해 제대로 개념정리가 안된 상태에서 만들려고 하니 우여곡절이 많았다. Ajax로 자바스크립트에서 데이터를 보내고, JAVA를 통해 DB에 저장하는 일련의 과정에서 GET/POST 방식의 차이점과, 어떤 것들을 매개변수로 받아서 서비스 클래스에서 그 변수를 활용해 DB에 넣을지(이 프로젝트는 STS를 이용하여 Spring Regacy Project로 만들어졌다.)...이를 통해  


