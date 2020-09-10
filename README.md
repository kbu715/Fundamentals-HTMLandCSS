parent + child : parent 선택자 다음에 오는 한개 item만 css를 먹인다.

parent ~ child : parent 선택자 다음에 오는 모든 형제 item들에 css를 먹인다.

.box p {

}


p {

}


이런 경우 올림픽을 생각해서 우선순위를 매긴다. ( id: 금, class,가상class: 은, tag: 동)



margin : 0px 0px 0px 0px (시계 방향을 생각한다. top right bottom left)


box-sizing : 기본적으로 content-box 

이걸 border-box


box type 

display : block 길막

margin이 자동으로 채워진다.

따로 width 설정을 안해주면 부모의 width를 따라간다.

자식들의 height 합이 부모의 height 값이다.

width height padding margin border 다 쓸 수 있다.

*margin : 0 auto ==> 중앙정렬??


*** block vs inline
    면(영역)    선(흐름)


display: inline 흐름
width, height, margin-top, margin-bottom, padding-top, padding-bottom,
border-top, border-bottom 쓸 수없다. 일렬로 흐르려는
흐름을 방해하기 때문에(사용해도 먹히지 않거나 룰브레이커가 되버린다.)


display: inline-block

영역으로서 흐름으로서 둘다 사용 가능





float 

1. what happens
-집나간 내새끼 찾을길 없네
-블록으로 신분상승
-길막을 못해 슬픈 블록!!
-텍스트나 이미지같은 inline의 요소를 갖고 있는 것들은 
float된 요소를 기기막히게 알아낸다. block의 요소를 갖고있는
것들은 알 수 없다.
-그리고 레이아웃 와장창!!
-요즘엔 거의 안쓰는게 사실..하지만 옛날코드를 볼때 자신있게
고치기위해선 알아야하긴해



ex)float:left --> 자기가 갈수있는 공간중에서 가장왼쪽으로 간다.


2. How to Fix it


-honeyful trick

float를 먹인 child가 있는데 부모에 overflow:hidden 을 주게 되면 
자식을 잡을 수 있다.


-Clearfix

clear:left  --> float:left를 먹인 걸 찾아라
clear:right
clear:both

*** clear 요소는 display: block 인 요소에만 쓸 수있다.


가상요소를 만들어서 clear:left를 해보자
parent::before -> parent의 첫번째 자식
parent::after -> parent의 가장 마지막 자식
::before
::after

.pseudo::before {
	content: '';
}





position: relative --> 내가 원래 있던 자리를 기준점으로 움직인다.
주변요소한테 아무런 영향을 끼치지 않는다.

position: absolute ==> float랑 거의 비슷

-집나간 내새끼 찾을길 없네
- 블록으로 신분상승
-길막을 못해 슬픈 블록아
-플로트 나만볼수있어요 x


자신을 감싸고 있는 여러 조상중에서 자신의 기준점을 선택한다

그중에서 position이 static이 아닌요소


position: fixed  --> absolute와 거의 비슷

다른점은 *viewport*를 기준으로 자신의 위치를 지정한다.


100vh : 100 viewport height 

ex) 1vh 1% viewport height

미디어쿼리
@media screen and (min-width: 578px){

	/* css 선언 */
}







flexbox


1.나, 플렉스박스 쓸거임

2.가로정렬 세로정렬?

3.무조건 한줄 안에 다정렬?

4.씐나는 플렉스박스 파티타임!



1.정렬하고자 하는 요소를 감싸는 부모에게 
display:flex


2.flex-direction : row|column

main axis
cross axis



3. flex-wrap : nowrap

감싸지 않고 자식의 사이즈를 줄여서라도 한줄로 정렬해버린다.


4.

main axis : justify-content
		flex-start | flex-end | center | space-between | space-around

cross axis : align-items | align-content


*align-items는 하나의 cross axis를 기준으로 정렬할때

그런데 flex-wrap:wrap일 경우 어떤 경우엔 

flex 라인이 두개가 생긴다.

이런경우에 align-content를 쓸 수 있다

그러면 flex 라인이 전체적으로 1개가 생겨서 그걸 기준으로 정해진다.


이렇게 복잡하게 생각안하고

그냥

선 align-items 후 align-content


order!!!

order이 진짜 쩌는것

order:1

순서를 바꿔버린다.