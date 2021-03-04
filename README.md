해당 저장소는 <a href="https://alvarotrigo.com/fullPage/ko/#page1">fullPage</a> JS 공식 홈페이지를 참고하여 만들어졌음을 밝힙니다.

<img src="gitImages\fullPage_Logo.png">

fullPage 라이브러리는 여러 대기업 회사 또한 사용하고 있으며 그저 이름대로 전체화면만 지원할 뿐 아니라 스크롤 이벤트 혹은 반응형 웹을 만들고 워드프레스를 이용하는 것에도 유용하게 사용된다.

React Angular Vue를 지원하며 이 또한 큰 인기를 얻게된 중요한 요인이라 볼 수 있다.

## 설치방법

NPM

```javascript
npm instlal fullpage.js
```

HTML

```html
<link rel="stylesheet" type="text/css" href="fullpage.css" />

<script src="vendors/easings.min.js"></script>

<script type="text/javascript" src="vendors/scrolloverflow.min.js"></script>

<script type="text/javascript" src="fullpage.js"></script>
```

css js 파일을 모두 불러오고 실행이 가능해진다.

## 실행 규칙

모든 하나 하나의 섹션은 fullpage라는 id값을 가진 div객체 안쪽에 들어가있어야 한다.

```html
<div id="fullpage">
    <div class="section">Contents</div>
    <div class="section">Contents</div>
    <div class="section">Contents</div>
    <div class="section">Contents</div>
</div>
```

### active

어떠한 특정 세션에서 시작하고 싶다고 정의하려면 class명에 active를 추가해주어야 한다.

```html
<div class="section active">Some section</div>
```

### slide

상, 하 로 구분되는 section단위가 아닌 좌우로 넘길 수 있는 슬라이드 단위의 컨텐츠를 생성하고 싶을 시 class명에 slide를 넣어주어야 한다. 즉 하나의 section블록에 안쪽으로 들어가는 셈

```html
<div class="section">
    <div class="slide">Slides</div>
    <div class="slide">Slides</div>
    <div class="slide">Slides</div>
    <div class="slide">Slides</div>
</div>
```

### VanilaJS 

아래와 같이 VanilaJS를 호환하려면 new로 새 생성자를 생성한 후 여러 옵션에 대한 값을 넣어주면 된다.

```javascript
var myFullpage = new fullpage('#fullpage', {
	//Navigation
	menu: '#menu',
	lockAnchors: false,
	anchors:['firstPage', 'secondPage'],
	navigation: false,
	navigationPosition: 'right',
	navigationTooltips: ['firstSlide', 'secondSlide'],
	showActiveTooltip: false,
	slidesNavigation: false,
	slidesNavPosition: 'bottom',

	//Scrolling
	css3: true,
	scrollingSpeed: 700,
	autoScrolling: true,
	fitToSection: true,
	fitToSectionDelay: 1000,
	scrollBar: false,
	easing: 'easeInOutCubic',
	easingcss3: 'ease',
	loopBottom: false,
	loopTop: false,
	loopHorizontal: true,
	continuousVertical: false,
	continuousHorizontal: false,
	scrollHorizontally: false,
	interlockedSlides: false,
	dragAndMove: false,
	offsetSections: false,
	resetSliders: false,
	fadingEffect: false,
	normalScrollElements: '#element1, .element2',
	scrollOverflow: false,
	scrollOverflowReset: false,
	scrollOverflowOptions: null,
	touchSensitivity: 15,
	bigSectionsDestination: null,

	//Accessibility
	keyboardScrolling: true,
	animateAnchor: true,
	recordHistory: true,

	//Design
	controlArrows: true,
	verticalCentered: true,
	sectionsColor : ['#ccc', '#fff'],
	paddingTop: '3em',
	paddingBottom: '10px',
	fixedElements: '#header, .footer',
	responsiveWidth: 0,
	responsiveHeight: 0,
	responsiveSlides: false,
	parallax: false,
	parallaxOptions: {type: 'reveal', percentage: 62, property: 'translate'},
	dropEffect: false,
	dropEffectOptions: { speed: 2300, color: '#F82F4D', zIndex: 9999},
	cards: false,
	cardsOptions: {perspective: 100, fadeContent: true, fadeBackground: true},

	//Custom selectors
	sectionSelector: '.section',
	slideSelector: '.slide',

	lazyLoading: true,

	//events
	onLeave: function(origin, destination, direction){},
	afterLoad: function(origin, destination, direction){},
	afterRender: function(){},
	afterResize: function(width, height){},
	afterReBuild: function(){},
	afterResponsive: function(isResponsive){},
	afterSlideLoad: function(section, origin, destination, direction){},
	onSlideLeave: function(section, origin, destination, direction){}
});
```

### anchors

```javascript
// http://alvarotrigo.com/fullPage/#(여기 들어갈 내용)
new fullpage('#fullpage', {
    // 해당 배열의 요소들이 저 곳에 들어감
    anchors: ['firstPage', 'secondPage', 'thirdPage']
})
```

자바스크립트로 조절하지 않는다고 해도 HTML로 설정이 가능하다.

```html
<div class="section">
    <!-- 클릭 시 data-anchor의 값으로 url이 바뀐다. -->
	<div class="slide" data-anchor="slide1"> Slide 1 </div>
	<div class="slide" data-anchor="slide2"> Slide 2 </div>
	<div class="slide" data-anchor="slide3"> Slide 3 </div>
	<div class="slide" data-anchor="slide4"> Slide 4 </div>
</div>
```

### 섹션 width, height

섹션의 높이를 자동으로 조절할 수 있다면 사용자는 별도의 스타일링 과정을 거치지 않고 편안한 작업이 가능할 것이다. 이는 fullPage JS가 지원하는데,

```html
<div class="section">전체 뷰포트 높이</div>

<div class="section fp-auto-height">자동 높이</div>
```

만약 옵션을 fp-auto-height-responsive로 설정한다면 브라우저 크기에 따라 다르게 설정되는 자동높이 값을 설정할 수도 있다.

이 외에도 다양한 상태의 Class를 지원한다.

<img src="gitImages\stateClass.png">

### 로딩 지연

첫 페이지가 로드될 때 모든 컨텐츠를 로드한다면 아마 버벅거리고 느려져 사용성이 현저하게 감소될 것이다.

이를 막기위해 fullPage JS는 지원하는 기능이 있는데 바로 Lazy Loading이다.

```html
<img data-src="image.png">

<video>
	<source data-src="video.webm" type="video/webm" />
	<source data-src="video.mp4" type="video/mp4" />
</video>
```

위와같이 기존 태그에 사용됐던 src속성을 data-src를 이용하여 바꾸어준다면 사용자가 사용할 때에 로드되어 불필요한 느려짐 현상을 줄일 수 있다.

만약 다른 방법으로 로드하여 Lazy Loading을 사용하고 싶지 않다면 위의 

```javascript
new fullpage('tag', {
	lazyLoading: false
})
```

을 주게되면 사용하지 않을 수 있다.

### 자동실행 및 미디어 일시정지

유튜브 iframe을 사용하거나 화면반응에 따라 자동실행 및 일시정지를 막고싶다면 아래와 같은 형식을 사용하여 서비스를 제공할 수 있다.

```html
<audio data-autoplay>
	<source src="oggfile.ogg" type="audio/ogg">
</audio>
```

위와같이 data-autoplay속성을 정의하거나 data-autoplay=1과 같이 true의 값을 넣어도 실행된다.

화면에서 영상 및 오디오가 벗어난다면 HTML의 기본 옵션으로 해당 매체는 정지된다. 이를 막고싶다면 아래 속성을 사용할 수 있다.

```html
<audio data-keepplaying>
	<source src="oggFile.ogg" type="audio/ogg">
</audio>
```