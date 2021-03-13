#  🌥️ Team MayWeather : Weather Wear 
<p align="center">
<img width="310" alt="스크린샷 2021-03-13 오후 7 17 54" src="https://user-images.githubusercontent.com/71998026/111027014-e75f2100-8430-11eb-90b6-b8e03cb229ed.png">
</p>




## BITCAMP 최종 프로젝트 WeatherWear : Closet 게시판 구현<br>(BITCAMP Final Project - Designing Closet Board)
사용기술 ( Technologies) : Java, Spring Framework, Javascript, Jquery, SPA(Single Page Application), MSA(Micro Service Architecture) 

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
게시판을 혼자 힘으로 구현해보는 것이 처음이었기 때문에, MVC Model과 Spring Framework에 대해 제대로 개념정리가 안된 상태에서 만들려고 하니 우여곡절이 많았다. Ajax로 자바스크립트에서 데이터를 보내고, JAVA를 통해 DB에 저장하는 일련의 과정에서 GET/POST 방식의 차이점과, 어떤 것들을 매개변수로 받아서 서비스 클래스에서 그 변수를 활용해 DB에 넣을지(이 프로젝트는 STS를 이용하여 Spring Regacy Project로 만들어졌다.)...변수명을 DB와 다르게 해서 에러가 뜨기도 했고, 매개변수를 잘못받아 DB에 저장이 되지 않을 때도 있었다. 그럴 때마다 하나씩 코드를 분석하고, 살펴보면서 MVC Pattern에 대한 이해가 높아졌다. 이 프로젝트를 통해 이제는 누군가가 게시판을 만들 수 있냐고 물어본다면 시간은 걸리겠지만, 구현할 수 있다고 자신있게 말할 수 있게 되었다.


##### 3) SPA / MSA
이 프로젝트는 5명의 팀원으로 구성되어 있고, SPA(Single Page Application), MSA(Micro Service Application)가 적용되어 있다. 처음 강사님으로부터 SPA/MSA를 프로젝트에 적용하라고 들었을 땐, 지금까지 배웠던 기존의 게시판 구성(여러개의 페이지를 두고, 그 페이지로 넘어가게 하는 것)이 아니라 처음 들어보는 개념에 당황하기도 하였지만, 팀원들끼리 의논하고, 강사님에게 자문을 구해 완벽한 SPA/MSA Application으로 만들 수 있었다. 이렇게 함으로써, 각 게시판 별로 DB를 가지고 있어 어느 한 곳에서 오류가 발생한다고 해도 다른 게시판에 영향을 미치지 않아 에러가 전체적으로 퍼질 우려도 지극히 적고, 필요에 따라 Ajax로 그 때 그 때 페이지를 호출해서 그려주기 때문에, 프로젝트 자체가 굉장히 가벼워 지는 것을 느꼈다. 물론, SPA의 단점인 뒤로가기를 구현하기가 어렵다는 점, 페이지 호출 시 매번 새롭게 페이지를 그려야 하기 때문에 속도가 떨어진다는 점이 있었지만, 그럼에도 불구하고 SPA 방식이 왜 업계에서 유행인지 알 수 있었다. 


##### 4) TEAMWORK
개발자를 꿈꾸는 사람으로서 웹페이지를 구현하는 팀프로젝트를 하게 된 건 처음인데, 개인이 하던 프로젝트와는 전혀 다른, 고려해야 할 점들이 많다는 것을 느꼈다. 통합할 때 회원 정보는 어떻게 가져올 것인지(Redis 이용), 같은 변수를 쓰는 곳은 없는지, 공통으로 사용하는 기능이 있다면 그 부분은 어떤식으로 이용할 것인지. 예전 직장에서의 협업과는 비슷하면서도 또 다르다는 생각이 강하게 들었고, 개발자로서 팀 프로젝트를 진행하기 위해서는 무엇보다도 팀원 간의 많은 의사소통이 필요하다고 느꼈다. 



