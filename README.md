# 스킵 내비게이션

웹 접근성 향상을 위한 국가표준 기술 가이드라인  
반복되는 링크를 건너뛸 수 있도록 건너뛰기 링크(Skip Navigation)를 제공해야 합니다.

스킵 내비게이션은 웹 페이지 상단에서 반복되는 콘텐츠를 건너뛰는 것이므로,  
스킵 내비게이션 이전에는 콘텐츠가 없어야 합니다.  
즉, <body>가 시작하고 바로 나오는 것이 가장 적절합니다.

```css
/* 스킵 내비게이션 */
#skip {
  position: relative;
}
#skip a {
  position: absolute;
  left: 0px;
  top: -35px;
  border: 1px solid #fff;
  color: #fff;
  background: #333;
  line-height: 30px;
  width: 140px;
  text-align: center;
}
#skip a:active,
#skip a:focus {
  top: 0;
}
```

# 이미지 표현 방법

1. img 태그로 표현 ( 의미가 있을 때 ) / alt 태그 - 대체 문자 표현
2. background 속성으로 표현 ( 의미가 없을 때 ) - 대체 문자 X
3. 이미지를 background 속성 - 웹 표준 준수하기 위해서는 가상으로 대체 문자를 만들어 줌 ( IR 효과 )
   이미지 스프라이트 효과

```css
/* IR 효과 */
/* 의미 있는 이미지의 대체 텍스트를 제공하는 경우 */
.ir_pm {
  display: block;
  overflow: hidden;
  font-size: 0;
  line-height: 0;
  text-indent: -9999px;
}
/* 의미 있는 이미지의 대체 텍스트로 이미지가 없어도 대체 텍스트를 보여주고자 할 때 */
.ir_wa {
  display: block;
  overflow: hidden;
  position: relative;
  z-index: -1;
  width: 100%;
  height: 100%;
}
/* 대체 텍스트가 아닌 접근성을 위한 숨김 텍스트를 제공할 때 */
.ir_su {
  overflow: hidden;
  position: absolute;
  width: 0;
  height: 0;
  line-height: 0;
  text-indent: -9999px;
}
```

# float: left 로 인한 영역 깨짐 방지법

1. 깨지는 영역에 똑같이 float: left 를 사용 -> 모든 박스에 float: left 사용하게 됨
2. float의 성질을 차단하는 clear: both; 를 사용 -> 어떤 영역이 깨졌는지 찾기 어려움
3. float을 사용한 상위 박스한테 overflow: hidden 을 사용 -> 현재는 제일 많이 사용
4. clearfix를 사용 -> 제일 좋은 방법

# jQuery 사용 (cdn 사용)

```html
<!-- jQuery 3.x -->
<script
  src="https://code.jquery.com/jquery-3.6.0.min.js"
  integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4="
  crossorigin="anonymous"
></script>
<!-- jQuery 2.x -->
<script
  src="https://code.jquery.com/jquery-2.2.4.min.js"
  integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44="
  crossorigin="anonymous"
></script>
<!-- jQuery 1.x -->
<script
  src="https://code.jquery.com/jquery-1.12.4.min.js"
  integrity="sha256-ZosEbRLbNQzLpnKIkEdrPv7lOy9C27hHQ+Xp8a4MxAQ="
  crossorigin="anonymous"
></script>
```

# slick.js 사용 (cdn 사용)

```html
<!-- 슬릭 사이트 : http://kenwheeler.github.io/slick/ -->

<link
  rel="stylesheet"
  type="text/css"
  href="//cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.css"
/>

<script
  type="text/javascript"
  src="//cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.min.js"
></script>
```
