# HTML

## 들어가기 전에

### 마크다운 비쥬얼 에디터 플러스인 설치

- markdown editor plugin 설치하기
- shift*2 > plugins
- [https://plugins.jetbrains.com/plugin/17254-markdown-editor](https://seango-jnu.github.io/webdev2022/html/)

## 확장자

- *.html
- *.htm 도 ok. but not recommend

## doctype

```html
<!DOCTYPE html>
```

- 필수 구문
- html5 문서임을 알려 준다.
- DOCTYPE 도 대소문자 구분하지 않음
- ```<!doctype html>``` 로 사용하겠습니다.
- 단축키(라이브템플릿 > Zen HTML) : ! + tab

### 바로 이전에 가장 많이 사용했던 doctype

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
        "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

- !!!xt + tab

- XHTML 1.0 Transitional

## comment

```html
<!--
    코멘트
-->
```

- 단축키 : cmd(ctr) + /
- 참고 : IE conditional comment
    - [https://www.quirksmode.org/css/condcom.html](https://seango-jnu.github.io/webdev2022/html/)

## html start

```html

<html lang="ko"></html>
```

- angle brackets 사용
- html tags 임을 알림

## head & body

```html

<html lang="ko">
<head></head>
<body></body>
</html>
```

- html 하위에는 head, body 태그만 올 수 있음.
- head, body 순서도 지켜는 것을 권장.

## head

```html

<head></head>
```

- 문서의 여러 정보를 나타내는 태그가 들어 옴
- title
- meta
- link
- script
- style
- noscript
- base

### title

```html
<title></title>
```

- 문서의 대표 제목
- 브라우저 타이틀에 표시됨
- 텍스트 타입의 정보만 넣을 수 있음.
- 다른 태그를 사용할 수 없음.(태그도 문자로 표시됨)

### meta

#### 자주 사용하는 meta tags

##### charset

```html

<meta charset="utf-8">
```

- 인코딩 지정없이 한글 html 파일 만들어 테스트 해보기
- 크롬 인코딩 변경을 위한 chrome extension
    - [https://chrome.google.com/webstore/detail/charset/oenllhgkiiljibhfagbfogdbchhdchml/related](https://seango-jnu.github.io/webdev2022/html/)

##### description

```html

<meta name="description" content="">
```

##### viewport

```html

<meta name="viewport"
      content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
```

- [https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag](https://seango-jnu.github.io/webdev2022/html/)
- [https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/UsingtheViewport/UsingtheViewport.html](https://seango-jnu.github.io/webdev2022/html/)
- 모바일 웹 대응
- 확대/축소 기능
- different screen resolution 대응

##### robots

```html

<meta name="robots" content="">
```

- all (색인 및 크롤링에 제한이 없는 기본값. index, follow 를 동시에 적용한 것과 동일)
- index (페이지가 색인되어 검색 결과에 표시될 수 있음)
- noindex (검색 결과에 페이지를 표시하지 않음)
- follow (페이지를 포함해 링크된 페이지를 검색할 수 있음)
- nofollow (페이지를 포함해 링크된 페이지를 수집하지 않음)
- none (noindex, nofollow 를 동시에 적용한것과 동일)

#### referrer

```html

<meta name="referrer" content="origin">
```

- referrer 로 origin 만 사용하겠다는 뜻
- default : strict-origin-when-cross-origin, path, query 사용
- https://example.com/page.html will send the referrer https://example.com/
- no-referrer : 레퍼러 정보를 표시하지 않음
- [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy](https://seango-jnu.github.io/webdev2022/html/)

##### http-equiv

- [https://www.w3schools.com/tags/att_meta_http_equiv.asp](https://seango-jnu.github.io/webdev2022/html/)
- meta tag 를 이용해서 http header 정보를 제공

```html

<meta http-equiv="x-ua-compatible" content="ie=edge">
```

- ie 혼환성 보기 설정
- ie 버전마다 렌더링 방법이 바뀌고 다르게 보이는 현상 발생에 대응.
- ie=edge : 호환성 보기 설정 무시.

```html

<meta http-equiv="refresh" content="2">
```

- 재미로 해보는 refresh

#### opengraph meta tags

```html

<meta property="og:title" content="">
<meta property="og:url" content="">
<meta property="og:image" content="">
<meta property="og:description" content="">
<meta property="og:type" content="article">
```

- https://ogp.me/
- 외부에 공유될 페이지의 정보를 직적접으로 관리함
- facebook, 다음댓글, 블로그... 등등에서 사용함

#### twitter card meta tags

```html

<meta name="twitter:card" content="">
<meta name="twitter:title" content="">
<meta name="twitter:description" content="">
<meta name="twitter:image" content="">
```

- [https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/markup](https://seango-jnu.github.io/webdev2022/html/)
- opengraph 와 중복되는 요소는 opengraph 만 사용해도 됩니다.
- [https://developer.twitter.com/en/docs/twitter-for-websites/cards/guides/getting-started](https://seango-jnu.github.io/webdev2022/html/)

##### apple meta tags

```html

<meta name="apple-mobile-web-app-title" content="AppTitle">
```

- Adding a Launch Icon Title
- [https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html](https://seango-jnu.github.io/webdev2022/html/)

### script

```html

<script></script>
<script src="" defer></script>
<script src="" async></script>
```

- body tag 에 올 수도 있음
- defer : 스크립트를 html parse 후에 로딩함
- async : 스크립트 로딩과 html parse 를 병렬로 진행함
- html 의 로딩을 빠르게 하기 위해 body 맨 아래 넣기도 함

### style

```html

<style></style>
```

- css 속성을 html 파일안에서 정의할 수 있음.
- html 보다 먼저 로딩되어야 해서 항상 head 태그 안에 넣음

### link

```html

<link rel="stylesheet" href="">
<link rel="icon shortcut" href="">
<link rel="apple-touch-icon" href="">
```

- html 에서 사용할 리소스를 로딩하기 위한 태그
- 대표적으로 css 파일, 파비콘 로딩에 사용함.
- html 보다 먼저 로딩되어야 해서 항상 head 태그 안에 넣음

### noscript

```html

<noscript>자바스크립트를 지원하지 않습니다.</noscript>
```

- 자바스크립트를 지원하지 않는 브라우저에서 보여 줌
- 테스트 : chrome dev tool > cmd + shift + p > disable javascript

## body

```html

<body class="" id="" style="" onload=""></body>
```

- body : 브라우저 화면에 보이는 태그가 들어 옴.
- class :
    - css/javascript 의 셀렉터 역할.
    - 동일이름 가능
- id :
    - css/javascript 의 셀렉터 역할.
    - 유일한 이름
- style : inline css 를 설정할 수 있음
- onload, onclick, onmouseover, onmouseout

### Block Elements

- [https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements](https://seango-jnu.github.io/webdev2022/html/)
- 줄바꿈 됨
- 부모 width 만큼 영역을 차지함

#### div

```html

<div></div>
```

- 눈에 보이는 효과 없음.
- 컨테이너의 역할을 함
- 동일한 스타일을 주기 위해 그룹핑 하기도 함

#### h1~6

```html
<h1></h1>
```

- h1 은 로고에 많이 사용됨

#### p

```html
<p></p>
```

- 문단을 표현하기 위한 태그

### hr

```html

<hr>
```

- 가로줄

### pre

```html

<pre></pre>
```

- preformatted text
- 보통 두칸 이상의 공백은 무조건 한칸으로 보이지만 pre 안에서는 모든 공백이 그대로 표현됨

#### ul

```html

<ul>
    <li></li>
    <li></li>
</ul>
```

- 순서가 없는 리스트를 나타내기 위한 태그
- 하위에 li 태그만 올 수 있음
- li 안에 모든 태그 가능

### ol

```html

<ol>
    <li></li>
    <li></li>
</ol>
```

- 순서가 있는 리스트를 나타내기 위한 태그
- 하위에 li 태그만 올 수 있음
- reversed
- type : a, A, i, I, 1
- start
- [https://developer.mozilla.org/en-US/docs/web/html/element/ol](https://seango-jnu.github.io/webdev2022/html/)

### dl

```html

<dl>
    <dt></dt>
    <dd></dd>
    <dt></dt>
    <dd></dd>
</dl>
```

- dl : description list
- dt : description term
- dd : description detail

#### table

```html

<table>
    <caption></caption>
    <colgroup>
        <col style="" class="">
        <col span="">
    </colgroup>
    <thead>
    <tr>
        <th colspan="" rowspan="" scope=""></th>
        <th></th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td></td>
        <td></td>
    </tr>
    </tbody>
    <tfoot>
    <tr>
        <td></td>
        <td></td>
    </tr>
    </tfoot>
</table>
```

- [https://developer.mozilla.org/en-US/docs/web/html/element/table](https://seango-jnu.github.io/webdev2022/html/)
- 위의 문서와 실습으로 알아 보겠습니다.

#### form

```html

<form action="" method="" target="">
    <fieldset>
        <legend></legend>
        <label for=""></label>
        <input type="text" value="" disabled readonly>
        <input type="hidden">
        <input type="search">
        <input type="color">
        <input type="date">
        <input type="button">
        <input type="file">
        <input type="email">
        <input type="password">
        <input type="image" alt="">
        <input type="checkbox">
        <input type="radio">
        <input type="range">
        <input type="reset">
        <input type="submit">
        <input type="tel">
        <input type="url">
        <input type="number">
        <button type="button"></button>
        <button type="submit"></button>
        <button type="reset"></button>
        <textarea rows="" cols=""></textarea>
        <select>
            <optgroup label="">
                <option></option>
            </optgroup>
        </select>
    </fieldset>
</form>
<header></header>
```

- 사용자 인터렉션을 위한 컴포넌트
- 모바일 웹에서 지원하는 type 이 많음
- label 권장함. 클릭하면 해당 컴포넌트 클릭한 효과 있음
- [https://developer.mozilla.org/en-US/docs/web/html/element/form](https://seango-jnu.github.io/webdev2022/html/)
- 위의 문서와 실습으로 알아 보겠습니다.

### Inline Elements

- [https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements](https://seango-jnu.github.io/webdev2022/html/)
- block 요소 안에 inline 요소가 올 수 있지만
- inline 요소안에 block 요소가 올 수 없음
- content 만큼 영역을 차지함

#### span

```html
<span></span>
```

- div 와 동일하지만 inline 요소임 : 줄바꿈 안됨.

#### b, strong
```html
<b></b>
<strong></strong>
```

- 굵은 글자 표시
- b : 화면상의 표시를 위함
- string : 문서의 의미적인 강조

#### i, em
```html
<i></i>
<em></em>
```

- 모두 이탤릭으로 표시됨
- i :  기술 용어, 외국어 구절
- em : emphasize, 강조

#### u

```html
<u></u>
```

- underline

#### sub, sup

```html
<sub></sub>
<sup></sup>
```

- sub : 아래 첨자
- sup : 위 첨자

#### small

```html
<small></small>
```

- 작은 글자

#### img

```html
<img src="" alt="" width="" height="">
```

- 이미지 리소스를 표시하는 태그
- 웹 접근성을 위해서 alt 속성을 꼭 넣어 줘야 한다.(스크리리더기를 위함)
- 지원 이미지 포맷
  - gif
  - jpeg
  - png
  - svg
  - apng
  - webp

#### br

```html
<br>
```

- 줄바꿈

#### iframe

```html

<iframe id="" name="" src="" width="" height="" title=""></iframe>
```

- 다른 html 페이지를 임베드할 수 있음
- 지도, 댓글, 광고 임베드, 폼데이터 전송에 많이 사용함

#### template

```html
<template></template>
```

- 보이지 않음
- html 을 담아 놓을 수 있음
- javascript 를 이용해서 html 을 사용할 수 있음

#### abbr

```html
<abbr></abbr>
```

- Abbreviation
- 약어

#### blockquote

```html
<blockquote cite=""></blockquote>
```

- 인용문
- cite 속성 : 출처

#### code

```html
<code></code>
```

#### picture

```html
<picture>
  <source srcset="" media="">
  <source srcset="mdn-logo-wide.png" media="(min-width: 600px)" />
  <source srcset="logo-768.png, logo-768-1.5x.png 1.5x" />
  <source srcset="photo.webp" type="image/webp" />
  <img src="" alt="">
</picture>
```

#### figure

```html
<figure>
  <img src="" alt="">
  <figcaption></figcaption>
</figure>
```

#### 영역 태그
- header
- section
- nav
- footer
- aside
- article
- main

#### 기능태그
- audio
- video
- canvas
- svg
- progress
- ruby

