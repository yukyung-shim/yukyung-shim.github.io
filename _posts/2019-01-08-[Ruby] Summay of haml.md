---
title: "[Ruby]haml 문법 구조 (Web, Ruby, rails)"
layout: posts
categories:
  - Web
last_modified_at: 2019-01-08T14:49:00+09:00

---

신규 프로젝트를 진행하면서 Ruby와 haml을 사용하게 되었다.  
직접 마크업을 작성할 일은 크게 없겠지만 읽을줄은 알아야 하니 간략히 정리해본다.  

추후 기회가 된다면 Ruby에 대해서 정리할 예정!  

> haml이란?
* Ruby의 .erb 파일을 쉽게 작성하기 위한 템플릿 엔진에서 시작되었다.
* CSS 부분은 SCSS와 동일하다.
* haml은 템플릿 자체에 HTML을 명시적으로 코딩할 필요가 없다. (동적 콘텐트를 생성하는 코드가 있는 HTML 자체에 대한 설명이기 때문!)


## 기본 예제  
html에서 태그의 시작과 끝이 있는 반면, haml에서는 앞에 %를 붙인다.  
(예: %p %a %strong %tr)
``` markdown
%div  //haml

<div></div> //html
```

## 아이디와 클래스를 넣는 방법

``` markdown
// 방법1. 짧고 간략한 방법
%div#contents.contents ContentsTag

// 방법2. 길지만 명확한 방법
%div{:id => "contents", :class => "contents"} ContentsTag

방법1, 방법2 모두 아래와같이 변환됩니다.
<div id="contents" class="contents"> ContentsTag </div>

```

## 복잡한 예제  
%tag 를 사용하지 않으면 기본으로 div로 인식한다!
``` markdown
#contents
  .left.table
    %table#tbl.tbl
      %tr
        %td
          %a#row.row table row
  .right
    =render :partial => "sidebar"
```

``` markdown
<div id="contents">
  <div class="left table">
    <table id="tbl" class="tbl">
      <tr>
        <td>
          <a id="row"> table row </a>
        </td>
      </tr>
    </table>
  </div>
  <div class="right">
    <%= render :partial => "sidebar" %>
  </div>
</div>
```


> 출처 및 참고 블로그  
<http://zinee-world.tistory.com/404>
