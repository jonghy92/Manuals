# Markdown Usage

<br>

<!-- header 사용법 -->
## header 사용법
header 을 사용하려면 적용 될 단어 앞에 " # "을 붙여야 함. </br>
붙이는 #의 갯수에 따라 제목의 크기가 다르게 적용 됨.
1~6 까지의 크기가 있음.

<br>

**input**:
```
# 1_header
## 2_header
### 3_header
#### 4_header
##### 5_header
###### 6_header
```
<br>

**output**:
> # 1_header
> ## 2_header
> ### 3_header
> #### 4_header
> ##### 5_header
> ###### 6_header

<br>


<!-- italic 사용법 -->
## Italic 사용법
italic 을 사용하려면 적용 될 단어 앞과 뒤에 " * "을 붙여야 함.

**input:**
```
it is *italic*
```

<br>

**output:**
> it is *italic*

<br>

<!-- bold 사용법 -->
## Bold 사용법
bold를 사용하려면 적용되어야 할 단어 앞과 뒤에 " ** "을 붙여야 함.

**input:**
```
it is **bold**
```

<br>

**output:**
> it is **bold**.

<br>


<!-- bold & italic 동시 사용법 -->
## Bold & Italic 같이 사용하는 법
bold & italic을 같이 사용하려면 적용되어야 할 단어 앞과 뒤에 " *** "을 붙여야 함.

**input:**
```
it is ***bold & italic*** 
```

<br>

**output:**
> it is ***bold & italic***


<br>


<!-- 문단의 간격 | 띄어쓰기 -->
## 문단의 간격 | 띄어쓰기
문단의 간격은 줄 바꿈으로 나태낼 수 밖에 없으며 여러 번 줄 바꿈은  `<br>` 로 가능함.

**input:**
```
문단 1 <br><br>
문단 2
```

<br>

**output:**
> 문단 1 <br><br> 문단2

<br>


<!-- 목록 - 순서 있는 목록 -->
## 순서 있는 목록
숫자와 " . "을 이용하여 작성함.

**input:**
```
1. 첫 번째
2. 두 번째
3. 세 번쨰
```
<br>

**output:**
> 1. 첫 번째
> 2. 두 번쨰
> 3. 세 번째

<br>


<!-- 목록 - 순서 없는 목록 -->
## 순서 없는 목록
-, *, + 를 이용해 작성함. (셋다 동일하게 작동)

**input:**
```
- 순서 없는 목록 1
    - 목록 1.1
        - 목록 1.1.1

* 순서 없는 목록2

+순서가 없는 목록3
    + 들여쓰기 (tab)를 하면 목록 아이콘이 다른 모양으로 표현 됨
    + 들여쓰기가 제대로 작동하지 않으면 스페이스바(4번)으로 대처 가능
```
<br>

**output:**
> - 순서 없는 목록 1
>   - 목록 1.1
>       - 목록 1.1.1
> + 순서 없는 목록 2
> + 순서 없는 목록 3
>   + 들여쓰기(tab)를 하면 목록 아이콘이 다른 모양으로 표현 됩니다.
>   + 들여쓰기가 제대로 작동하지 않으면 스페이스바(4번)으로 대체할 수 있음

<br>


<!-- 폰트 스타일 -->
## 폰트(font) 스타일
굵게, 기울여 쓰기, 취소선을 쓸 수 있음

**input:**
```
__굵게__
**굵게**

_기울여 쓰기_
*기울여 쓰기*

~~취소선~~
```

<br>

**output:**
> __굵게__ <br>
> **굵게** <br>
> 
> _기울여 쓰기_ <br>
> *기울여 쓰기_ <br>
>
> ~~취소선~~

<br>


<!-- 인용문 -->
## 인용문
인용문을 작성할 떄에는 ' > ' 를 사용

**input:**
```
> Hello World!

> 인용문
>> 우측 꺾쇠(>)의 개수에 따라 중첩 가능
>>> 인용문
```

<br>

**output:**
> Hello World!

> 인용문
>> 우측 꺾쇠(>)의 개수에 따라 중첩 가능
>>> 인용문

<br>


<!-- 인라인 코드(Inline Code) -->
## 인라인 코드 (Inline Code)
인라인 코드는 백틱( ` )을 감싸 표현함

**input:**
```
`인라인 코드 작성`
```

<br>

__output:__
> `인라인 코드 작성`


<br>


<!-- 여러 줄로 된 코드 블럭 (Code Block) -->
## 코드 블럭 (Code Block)
블럭 코드는 백틱을 세 개 ```감싸 표현함

__input:__
```
` ` `
위 아래 3개로 감싸면 블럭을 만들 수 있음
` ` `
```
<br>

__output:__
> ```
> 위 아래 3개로 감싸면 블럭을 만들 수 있음
> ```

<!-- 코드 하이라이트 -->
## 코드 하이라이트 (Code Highlight)
백틱 ( ` ) 3개를 코드블럭 만들때 처럼 입력 후, 코드의 언어 이름을 입력함

__input:__
```python
` ` `python
for i in range(10):
    print("Hello World")
` ` `
```
<br>

__output:__
>```python
>for i in range(10):
>   print("Hello World")
>```



<!-- 링크 (Link) -->
## 링크 (Link)
인라인 링크와 url 링크, 참조 링크로 나타낼 수 있음


__input:__
```
인라인 링크:
[인라인 링크](https://google.com)

url 링크:
<https://google.com>

참조 링크:
[참조 링크] : (https://google.com "설명글을 쓰면 됨")
```

<br>

__output:__
> 인라인 링크: <br>
> [인라인 링크](https://google.com) <br>
> <br>
> url 링크: <br>
> <https://google.com> <br>
> <br>
> 참조 링크: <br>
> [참조 링크] : (https://google.com "설명글을 쓰면 됨")

<br>

<!-- 수평선 -->
## 수평선 (Horizontal Line)
`*` 이나 `-`, `_` 등을 3개 이상 입력하면 작성할 수 있고,
띄어쓰기를 중간에 삽입하여도 가능함. 

__input:__
```
***
------
__ __ __ __ __
<hr>
```

<br>

__output:__
> ***
> ------
> __ __ __ __ __
> <hr>

<br>


<!-- 이미지 링크 -->
## 이미지 링크
1. 이미지 링크는 작성시 `![이미지 설명](이미지 링크)`로 표기
2. 이미지에 링크를 걸고 싶을 떄에는 `[![이미지 설명](이미지링크)](연결하고자하는 url "마우스를 올렸을시 나타나는 문구")`
3. HTML 태그 `<img>` 사용 하여 이미지 사이즈 조절



__input:__
```
<!-- 이미지 링크 띄우는 법: -->
![다크나이트][https://ew.com/thmb/ttPpq_6kOyc2v51V-__KwRl29iM=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/batman-forever_l-d8bbd60a3bb14d80b2fa266d9d0727fb.jpg]


<!-- 이미지 띄우고 url과 설명 포함: -->
[![다크나이트](https://ew.com/thmb/ttPpq_6kOyc2v51V-__KwRl29iM=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/batman-forever_l-d8bbd60a3bb14d80b2fa266d9d0727fb.jpg)](https://ew.com/thmb/ttPpq_6kOyc2v51V-__KwRl29iM=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/batman-forever_l-d8bbd60a3bb14d80b2fa266d9d0727fb.jpg "다크나이트 출처 url:")
```

<br>

__output:__
> ##### 예시 1:
> ![다크나이트](https://ew.com/thmb/ttPpq_6kOyc2v51V-__KwRl29iM=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/batman-forever_l-d8bbd60a3bb14d80b2fa266d9d0727fb.jpg)

> ##### 예시 2:
>[![다크나이트](https://ew.com/thmb/ttPpq_6kOyc2v51V-__KwRl29iM=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/batman-forever_l-d8bbd60a3bb14d80b2fa266d9d0727fb.jpg)](https://ew.com/thmb/ttPpq_6kOyc2v51V-__KwRl29iM=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/batman-forever_l-d8bbd60a3bb14d80b2fa266d9d0727fb.jpg "다크나이트 출처 url:")


> ##### 예시 3:
> <img src="https://i.redd.it/r05ztg2zp6q81.jpg" width="200" height="400" >

<br>


<!-- 테이블 -->
## 테이블
테이블은 `(|)`로 구분하며 사용하는데, 중간에 하이픈이 들어간 줄은 꼭 있어야 하며, 콜론 `(:)` 을 왼쪽에 넣으면 왼쪽 정렬, 양쪽에 넣으면 중앙 정렬, 오른쪽에 넣으면 오른쪽 정렬이 됨

__input:__
```
|학생명|자료구조|알고리즘|컴퓨터구조|
|:---:|:---:|:---:|:---:|
|이종현|A|A|A|
|이승연|F|F|F|
```
<br>

__output:__
>|학생명|자료구조|알고리즘|컴퓨터구조|
>|:---:|---:|:---:|:---|
>|이종현|A|A|A|
>|이승연|F|F|F|

<br>

<!-- 체크박스 -->
<!-- MarkDown All in One 다운받으니 체크박스 해결됨 -->
## 체크박스 (Check Box)
`-`, `*`, `+` 뒤에 띄워쓰기 후 대괄호를 띄워서 써주면 됨

__input:__
```
- [ ] batman 블러그 구경
- [X] batman 블러그 구경 
```

<br>

__output:__
> - [ ] batman 블러그 구경
> - [X] batman 블러그 구경 

<br>

<!-- 이모지 (Emoji) -->
## Emoji (이모티콘)
이모지는 이모지 창을 열어서 작성함:
- 윈도우는 : `windows` + `.`
- 맥은 : `command` + `control` + `spacebar`

__output:__
```
😊
```
<br>

<!-- 글자 색상 -->
## 글자 색상 & 응용
HTML(CSS) 문법으로 사용 가능

__input:__
```
<span style="color:red"> 빨간 글씨 </span>

<span style="background-color: yellow"> 형광펜 색칠 </span>

<div style="color:red; background-color:yellow"> 형관펜 색칠 2 </span>
```

<br>

__output:__
> <span style="color:red"> 빨간 글씨 </span> <br>
> <span style="background-color: yellow"> 형광펜 색칠 </span> <br>
> <div style="color:red; background-color:yellow"> 형관펜 색칠 2 </span>

<br>

<!-- 마크다운 기호 그대로 출력 -->
## 마크다운 기호 그대로 출력
마크다운 기호를 그대로 출력하기 위해서는 앞에 역슬래시 `\`를 붙여주면 됨

__input:__
```
\*
\_
\#
\+
\-
\!
\\
\<br>
\``````
```
<br>

__output:__
> \* <br>
> \_ <br>
> \# <br>
> \+ <br>
> \- <br>
> \! <br>
> \\ <br>
> \<br> <br>
> \``````

<br>
<br>



## ref:
https://www.youtube.com/watch?v=OoeGqYu8JFQ







