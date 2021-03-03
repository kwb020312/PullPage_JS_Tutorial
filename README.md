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