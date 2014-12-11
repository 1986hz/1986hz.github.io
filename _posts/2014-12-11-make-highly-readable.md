---
layout: post
title:  "문서 가독성 높이기"
date:   2014-12-11 23:29:27
categorie: blog
---

**가독성**은 문서를 빠르고 정확하고 쉽게 읽혀 이해하는 정도로 생각할 수 있다. 그럼 문서의 가독성이 높으면 읽기 좋은 문서라는 것을 알 수 있다. jekyll에서 기본적으로 제공되는 css스타일은 영어를 기준으로 되어 있어서 한글에서 그대로 사용하기에는 가독성이 떨어진다. 그래서 이 문서에서는 한글 문서의 가독성을 높이기 위한 방법을 몇가지 기록한다.


## 참고사이트
- [웹나눔고딕 폰트 적용하기](http://api.mobilis.co.kr/webfonts/font_usage.html?fontface=NanumGothicWeb)
- [가독성 높이는 방법](http://yongja.tistory.com/23)


## 나눔고딕폰트을 기본폰트로 사용하기
최근 웹에서 본 한글폰트 중 개인적으로 가장 가독성이 높은 폰트는 **나눔고딕폰트**인 것 같다. 그래서 나는 블로그의 기본폰트를 나눔고딕폰트로 사용할 것이다.

- _includes폴더에 있는 head.html파일에 있는 `<head>`와 `</head>`사이에 `<link href='http://api.mobilis.co.kr/webfonts/v2/css/NanumGothicWeb' rel='stylesheet' type='text/css'/>` 코드를 추가한다.
{% highlight html %}
<head>
    ...
    <link href='http://api.mobilis.co.kr/webfonts/v2/css/NanumGothicWeb' rel='stylesheet' type='text/css' />
</head>

{% endhighlight %}

- css폴더에 있는 main.scss파일을 있는 `$base-font-family`를 `NanumGothicWeb`로 수정한다.
{% highlight html %}
$base-font-family: NanumGothicWeb;
{% endhighlight %}


## 글짜크기와 줄간격 수정하기
작은 글짜 보다는 큰 글짜가 읽기가 쉬우며, 줄간격이 넓으면 글을 읽는데 집중할 수 있으므로 가독성을 높일 수 있다.

- css폴더에 main.scss에서 `$base-font-size:`의 값을 **18px**로 수정하고 `$base-line-height`의 값을 **1.8**로 수정한다.


## 소제목 밑에 라인 넣기
markdown으로 문서를 작성시 `##`으로 html의 h2효과를 낼 수 있다. 그리고 `##`으로 문서에서 주로 소제목으로 사용되는데 이때 소제목 밑에 라인이 있다면 소제목이 눈에 잘 들어오므로 문서의 흐름을 빨리 집을 수 있어 이해도를 높일 수 있다. 

- _sass폴더에 있는 _layout.scss에서 h2구문을 찾아 아래와 같이 `border-bottom: 1px solid $grey-color-light;`를 추가한다.
{% highlight html %}
h2 {
    font-size: 32px;
    border-bottom: 1px solid $grey-color-light;

    @include media-query($on-laptop) {
        font-size: 28px;
    }
}
{% endhighlight %}