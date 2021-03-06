---
title: "[깃 블로그]마크다운 사용법 정리"
layout: posts
categories:
  - blogging
last_modified_at: 2019-01-06T13:00:00+09:00

---

## 1. 제목 태그(h 사용)

``` markdown
  # : h1
  ## : h2
  ### : h3
  ...
  ####### : h7
```


## 2. 블럭인용문자 : >
> 블럭인용문자 '>' 사용
>> 중첩된 인용문자 '>>' 사용


## 3. 순서있는 목록 : 숫자 + . 이용
1. 순서1
2. 순서2
3. 숫자3
5. 숫자5


``` markdown
1. 순서1
2. 순서2
3. 숫자3
5. 숫자5  
위와 같이 입력했지만 입력숫자에 상관없이 내림차순으로 표시된다!
```


## 4. 순서 없는 목록 : *, +, -사용
* 입력*
  + 입력+
    - 입력-


## 5. 코드사용 : <pre><code></code></pre>
```markdown
<pre>
  <code>
    <p> 코드부분! </p>
  </code>
</pre>
```


## 6. 수평선 사용

``` markdown
* * *
***
*****
- - -
---------------------------------------
```

- 위와 같은 text를 이용하면 아래와같이 수평선이 표시된다.

* * *
***


## 7. 링크사용
* 참조링크<br>

``` markdown
Link: [google][googleLink]
[googleLink]: https://www.google.com

[link keyword][id]
[id]: URL "Optional Title" 형식으로 연결
```

* 인라인 링크<br>

``` markdown
Link: [google](<https://www.google.com>)

[title]('< link >') 형식으로 연결
```

* 자동연결<br>

``` markdown
Link : <https://www.google.com>

< link > 형식으로 바로 연결
```


## 8. 글씨사용

``` markdown
* 보통 *
** 굵게 **   
~~ 취소선 ~~
```
- '*' : 보통, '**' : 굵게, '~~': 취소선, 'br tag 또는 띄어쓰기 두번' : 줄바꿈


# 9. 영역에 내용 입력

``` markdown
  (``` markdown
   '내용'
  ```)
   위와 같은 형식으로 감싸준다!(괄호 제외)
```
