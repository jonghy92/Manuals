<!-- python signs info -->
# Python Signs Info (특수기호 활용)

### 노트 순서:
1. *, **
2. :, ->
3. ...
4. @
5. %


<br>

## *, ** 사용:
*(asterisk)는 곱하기(연산자) 외에도 몇가지 다른 용도로 사용가능함.

<br>

1. __'*' (Everything, 모든 것):__ <br>
일반적으로 프로그래밍에서 *는 모든 것(Everything)의 의미로 사용됨.

    ```python
    from math import *
    ``` 
    위 코드는 math라는 라이브러리에서 모든 변수, 함수, 클래스를 가져온다는 의미임. <br>
    (하지만 상위 코드처럼 모든 변수,함수,클래스를 필요치 않은데 가져오는것은 낭비라 추천하지 않음...)

<br>

2. __*args, **kwargs (가변인자):__ <br>
보통 함수(def)를 만들면 인자(argument)를 넣게끔 설계하는데, 이때 들어가는 인자의 개수를 정하고 싶지 않을 때 *args(arguments)를 사용함. 

    ```python
    ## *args
    def my_family_list(*args):
        print(args)

    my_family_list("father", "mather", "brother", "sister")
    
    # *args output
    >>> ("father", "mather", "brother", "sister")    
    ```
    
    <br>

    Dictionary(딕셔너리) 형식으로 인자를 넣을땐 **kwargs (keyword arguments)를 사용:
    ```python
    ## **kwargs
    def my_family_age(**kwargs):
        print(kwargs)
    
    my_family_age(father="66", mather="65", brother="32")

    # **kwargs output
    >>> {'father': '66', 'mather': '65', 'brother': '32'}
    ```

<br>

## :, -> 사용:
파이썬에서 함수를 정의할 때, __:__ 와 __->__ 를 주석으로 쓸 수 있음. 구체적으로, 안전한 프로그래밍을 위해 함수를 정의할 때 변수의 자료형태(type)와 return값의 자료형태(type)을 명시하는 용도로 사용됨. <br>
(코드의 작동에 영향을 주지는 않지만, 실수를 미연에 방지하는 프로그래밍을 가능하게 한다고 함)

<br>

```python
## type hint 적용
def make_character(name:str, age:int) -> str:
    character = name + str(age)
    return character

make_character("batman", 33)

# output
>>> 'batman33'
```

<br>


## ... (Ellipsis) 사용:
__Ellipsis(...)__ 는 여러 용도로 활용될 수 있는데, 파이썬의 '__:(콜론)__', '__pass(작동 없음)__', 및 __FastAPI__ 백엔드 라이브러리에서 활용이 가능하다.


<br>

## @ (decorator) 사용:
@는 데코레이터(decorator)라고 불리며, 함수에 무언가 내용을 추가하고 싶을때 사용됨. 단순히 함수에 바로 내용을 추가하지 않고 데코레이터를 쓰는 이유는 다른 함수들에도 반복적으로 추가할 수 있도록 관리하기 위해서임.

<br>

```python
## decorator def made
def decoratormade(func):
    print("decoration - start")
    func()
    print("decoration - end")

## decorator used
@thisisdecorator
def decoratorused():
    print("function - used")


# output
>>> decoration - start
>>> function - used
>>> decoration - end
```
<br>

## % 사용:
__%__ 는 파이썬에서 문자열 포메팅(string formatting)을 할 떄 사용됨.
문자열 포메팅이란 출력하는 문자열의 특정 위치에 특정한 값(변수)을 삽입하여 출력하는것을 의미함. 

% 뒤에는 자료형을 가리키는 문자를 사용하여야 함. <br>
1. __%s__ : 문자열
2. __%d__ : 정수
3. __%f__ : 실수

<br>

```python
name_list = ["lee", "park", "kim"]
for i in name_list:
    print("My name is %s" % i)

>>> "My name is lee"
>>> "My name is park"
>>> "My name is kim"
```