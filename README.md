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



Media Query

mobile부터 하는게 좋다.










typography 타이포그래피


font-size

단위 px em rem

px : 절대단위

em rem : 상대 단위

em : 실제로 적용된 폰트 사이즈(자연스럽게 먹은 폰트사이즈)

사람들이 잘안씀..


rem : root em 

여기서 root=html

html {
	font-size: 20px;
}

p {
	font-size: 3rem;
}

최종으로 그럼 60px이 된다.


line-height : em을 많이 사용한다.

em 단위를 생략해주는게 관례이다

line-height : 1.5;


letter-spacing : 자간, px, em 사용한다. 보통은 em 많이 사용한다.



font-family : "Poppins", sans-serif;

--> 파핀스 없으면 sans-serif 체 중에 아무거나 써줘!!


font-weight  : 폰트의 굵기, 무조건 100씩 커진다.

ligh: 300

regular : 400

bold : 700

400,700 \중요

color : #0066ff; ---- 방식이 세가지가 있다.

1. #0066FF;
2.rgba(0,102,255,1) 투명도까지
3.그냥 blue



text-align : left | right | center;


text-indent : (들여쓰기) 10px;

text-transform : none | capitalize | uppercase | lowercase

capitalize : 모든 단어의 첫글자 대문자로




text-decoration : a태그 쓸때 text-decoration : none; 밑줄없앨때 가장 많이 쓴다.

font-style : italic 이것만 기억하면된다.



Webfont

fonts.google.com



transition!!!

property	duration [timing-function] [delay] ([]: 생략가능한 속성)

*timing-function : 변하는 속도에 대한 설정

ease-in | ease-out | ease-in-out | cubic-bezier()


ex) transition: font-size 2500ms ease-in 1000ms; 
//1초후에 2.5초동안 글자 크기 ease-in 트랜지션

ex transition: all 1500ms // 모든 속성을 1.5초동안

ex)transition: font-size 1000ms ease-out, background-color 2000ms cubic-bezier(0.08, 0.57, 0.97, -0.78) 1000ms;
이렇게 두개의 속성에대해 따로 설정 가능



background-color: url();

background-repeat: no-repeat;

background-size: contain | cover | custom

contain: 요소안에 이미지가 다 들어가게

cover: 요소안이 꽉차게 이미지가 잘리더라도


background-position: center center; (x, y 축으로 어느지점에)



가상요소 ::after ::before는 기본적으로 inline






애니메이션부터

@keyframes


@keyframes name {

	from {
		/* Rules */
	}

	to {
		/* Rules */
	}
}


or,

@keyframes name {

	0% {
		/* Rules */
	}

	50% {
		/* Rules */
	}
	10 0% {
		/* Rules */
	}
}




.box {
	animation-name: name;
	animation-duration: 2000ms;
	animation-timing-function: ease-in-out;
	animation-delay: 1000ms;
	animation-iteration-count:3 | infinite;
	animation-direction: alternate(번갈아가면서)
}





overflow

visible | hidden | auto | scroll


auto/scroll 거의비슷





transform (진정한 css 장인들의 세계)


1. translate() - translateX, translateY 
다른 요소들에게 영향을 안준다. 그대로있다. 다른요소들이 translate 되기전 위치를 알고있다.
eX) translate(100%, 100%) 이라면 딱 자기 사이즈 만큼 움직인다.
2. rotate()
ex) rotate(45deg)
3. scale()
ex) scale(0.5) 사이즈가 반으로 줄어든다.

이 세개만 자주 쓴다.



transform은 자주 사용하진 않는다. 그나 transform: translate(-50%, -50%) : 가운데 배치할때


visibility : 그냥 보이지만 않게 자리에는 존재한다. visible | hidden

display:none 은 존재하지 않게 한다!!!




Box Shadow 요소에 그림자를 줄때 사용하는 property


| h-offset v-offset blur spread color | 이 순서대로 꼭 적어줘야 한다.

휴먼랭기지로 말하자면

x, y, 흐린정도 그림자사이즈, 색상



요즘대세

neumorphism.io






grid system

container 
column
gutter




bootstrap

container -> row -> col 이 순서대로 감싼다.

col-12 col-md-6 col-lg-4 col-xl-3