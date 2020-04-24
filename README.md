# Python
파이썬(영어: Python)은 1991년 프로그래머인 귀도 반 로섬(Guido van Rossum)이 발표한 고급 프로그래밍 언어로, 플랫폼에 독립적이며 인터프리터식, 객체지향적, 동적 타이핑(dynamically typed) 대화형 언어이다. 파이썬이라는 이름은 귀도가 좋아하는 코미디 〈Monty Python's Flying Circus〉에서 따온 것이다.
파이썬은 비영리의 파이썬 소프트웨어 재단이 관리하는 개방형, 공동체 기반 개발 모델을 가지고 있다. C언어로 구현된 Cython 구현이 사실상의 표준이다.
참고: [위키백과, 파이썬](https://ko.wikipedia.org/wiki/%ED%8C%8C%EC%9D%B4%EC%8D%AC)


python 공부 내용 정리. 참고:[생활코딩](https://opentutorials.org/course/1)

2020.04.22까지 정리내용


## Python 실행
cmd 입력: window+r
### 대화형 모드 실행: 복잡한 프로그램 작성에 어려움.

cmd 창에 직접적으로 실행
```
python
print('hello world')
Ctrl+c  #작업을 끝냄 
```

### 파일 모드 실행

메모장 사용, 저장시 .py파일로 저장, 모든파일, utf-8
```
저장 위치 복붙 #파일탐색기에서 해당 파일 우클릭 후 속성 참고ex)C:\Users\hikyj\OneDrive\text\python_ruby
```


## 수와 계산
숫자를 프로그래밍적으로 표현하는 방법(문법)
### 사칙연산
```
print(10+5)
print(10-5)
print(10*5)
print(10/5)
```

### 살짝 복잡한 계산

정수와 실수 인식됨.
```
import math               #가져옴/수학적계산
print (math. ceil(2.2))   #올림->3
print (math. floor(2.7))  #내림->2
print (math. pow(2,10))   #2의 10승->1024
print (math. pi)          #원주율 출력->3.141592653589793
```


## 문자와 데이터 타입
### 문자의 표현

문자열(string)
```
print('Hello')          #Hello
print("Hello")          #Hello
print("Hello 'world'")  #Hello 'world'
print('Hello "world"'   #Hello "world"
```
("''") or ('""')가능. 문자열의 시작과 끝을 나타내기 때문.(문자열로 인식하기 시작하기 때문.)

('''') or ("""")의 경우 syntax error 발생

### 문자열의 제어(문자연산)
```
print('Hello '+'world') #문자열을 더함. Hello world
print('Hello '*3)       #문자열을 숫자 만큼 반복. Hello Hello Hello 
print('Hello'[0])       #H  :0 번째 문자를 출력
print('Hello'[1])       #e  :1 번째 문자를 출력
print('Hello'[2])       #l  :2 번째 문자를 출력
```
문자연산에는 +, * 만 존재

### 문자열의 제어2
```
print('hello world'.capitalize())                     #Hello world  :첫 번째 문자만 대문자로 표시
print('hello world'.upper())                          #HELLO WORLD  :모든 문자를 대문자로 표시
print('hello world'.__len__())                        #11 :문자의 개수
print(len('hello world'))                             #11 :문자의 개수
print('Hello world'.replace('world', 'programming'))  #Hello programming  :'world'를 'programming'으로 변환
```
replace('a', 'b'): 텍스트 편집기능(find and replace) 바꾸기 원하는 텍스트를 찾아 바꿔줌

### 특수한 문자들
- escape: \
- new line: \n
- tap: \t
- alert: \a
```
print("egoing's \"tutorial\"")  #egoing's "tutorial" :' 또는 " 앞에 붙어 일반문자로 해석하기 위해 사용
print("\\")                     #\ :\를 화면에 표시하고 싶을 때
print("Hello\nworld")           # :줄바꿈
print("Hello\t\tworld")         # Hello       world:tap 2번
print("\a")                     #   :경고음 울림
print('Hello\nworld')           # :""과''의 역할이 거의 동일
```
print("\") ->오류, 닫히지 않은 문자로 인식

### 문자와 숫자를 통해서 알아보는 데이터 타입

10과 "10"은 다르다
```
print(10+5)       #15 :산술연산
print("10"+"5")   #105 :문자연산
```


## 변수
### 변수의 기본 문법

변수=숫자, 변수=문자열
```
x=10
y=5
print(x+y)                #15
 
title = "python"
print("Title is "+title)  #Title is python
```

### 문자열에서 변수의 사용

긴 문장 내 중복되는 단어 또는 분장을 변수로 바꿔준다. 같은 코드를 여러번 반복해야할 때, 변수만을 바꿔 사용할 수 있다.

중복을 제거, 반복을 제거한다.
```
name = "김유진"
print("안녕하세요. "+name+"님")                #안녕하세요. 김유진님
print(name+"님을 위한 강의를 준비했습니다.")    #김유진님을 위한 강의를 준비했습니다.
print(name+"님 꼭 참석 부탁드립니다.")          #김유진님 꼭 참석 부탁드립니다.
```
print("안녕하세요. name님") -> name을 문자열로 인식하게 된다. 따라서

- 안녕하세요._ 와 님을 문자열(" ")로 작성
- +를 작성하여 변수가 가지고 있는 문자열과 결합

### 수 계산에서의 변수의 사용

다음은 장학재단이 한명의 학생에서 1년에 a만원을 후원한다고 가정할 때, c명의 후원자가 돈을 얼만큼 내야 후원을 받을 수 있는 학생수가 b명이 되는지를 계산하는 과정이다.

이는 계산 후 대입을 하는 방식으로, 공식을 만들고 변수를 사용하여 해당 변수의 대입값에 혼동이 오지 않도록 한다.->대수학
```
donation = 200  #a
student = 10    #b
sponsor = 100   #c
print((donation*student)/sponsor) #20
```
따라서 후원자 1인당 20만원을 부담해야한다.


## 개발도구
편리성이 증가할수록 안전하게 사용할 수 있는 훈력과 교육을 요구하고, 위험도가 증가한다.

- ATOM: 편집기
- [IDE](https://www.jetbrains.com/pycharm/): 통합 개발 도구->데이타 베이스 제어, 소스코드를 제어하는 버전관리, 편집기


## 비교와 블리언(Boolean)
숫자의 대소관계
- 숫자, 문자: 많은 값들로 이루어져있는 데이터 형식 
- 블리언: 조건문, 반복문의 핵심적 역할을 하는 도구, 참과 거짓 두개의 값으로만 이루어짐.

george bool를 기림

비교연산자
```
a=1
b=1
print(a==b)   #True
print(1==2)   #False
print(1>2)    #False
print(1<2)    #True
print(True)   #True
print(False)  #False
```


## 조건문(Conditional Statements)
### 기본문법 (조건이 없는 경우)
```
if False:
    print("code1")
    print("code2")  #조건문의 끝을 구분하는 기준: 공백(들여쓰기)을 가지고 있는 명령문을 같은 그룹으로 인식
print("code3")      #if문 바깥에 존재
```
결과: code3
- true->실행
- false->실행되지 않음

### 조건문의 활용

조건문 뒤에는 비교연산자가 온다.

로그인 프로그램(true 일때만 반응)-동등비교연산자
```
input = 11
real = 11
if real == input:
    print("Hello!")
```
결과
```
Hello!
```

### else: 한가지 조건에 반응

a != b :a와 b가 다른가?
```
input = 22
real = 11
if real == input:
    print("Hello!")
else:
    print("Who are you?")
```
결과
```
Who are you?
```

### else if: 여러가지 조건에 반응

elif->가독성과 코드간의 통합성을 높임.

문제점: 입력값과 출력값을 조정해 주어야 함.

str: 문자열(string)
```
in_str = "ab"
real_yj-kim-00 = 11
real_k8805 = "ab"
if real_yj-kim-00 == in_str:
  print("Hello!, yj-kim-00")
elif real_k8805 == in_str:
  print("Hello!, k8805")
else:
  print("Who are you?")
```
결과
```
"Hello!, k8805"
```

## 입력과 출력
### 사용자의 입력을 애플리케이션으로 가져오기

입력값에 따라 다르게 동작
- input 함수: 1. 프로그램의 동작 중지 2. 입력 후 enter 3. input함수가 입력값으로 변경되어 변수의 값으로 저장됨.
- a.upper: a변수를 대문자로 출력
```
in_str = input("입력해주세요.\n") #입력해주세요, 줄바꿈 후 입력값을 넣도록 설정됨.
print(in_str.upper()+" World!")  #입력값을 항상 대문자로 출력하도록 설정
```
결과
```
입력해주세요
hello
HELLO World!
```

### 로그인 애플리케이션에 입력기능 추가하기
```
in_str = input("아이디를 입력해주세요.\n")
real_yj-kim-00 = "11"                        #문자열로 설정해주어야 한다.
real_k8805 = "ab"
if real_yj-kim-00 == in_str:
  print("Hello!, yj-kim-00")
elif real_k8805 == in_str:
  print("Hello!, k8805")
else:
  print("Who are you?")
```
결과
```
아이디를 입력해주세요
11
Hello!, yj-kim-00
```

*주의!* 숫자가 문자열로 인식된다.
```
in_str = input("아이디를 입력해주세요.\n")
print(type(in_str))
```
결과
```
아이디를 입력해주세요.
11
<class 'str'>
```

## 논리 연산
### 논리 연산자란?
왼쪽과 오른쪽에 블리언이 온다.
- and: 양쪽 모두 만족해야 true
- or: true가 이김
- not: 오른쪽에만 블리언이 오고, 오른쪽 블리언과 반대되는 결과를 내놓는다.

### OR
in_str이 하나의 real_값을 만족하기만 하면 로그인을 시켜주는 프로그램. 그렇지 않은 경우 Who are you?
```
in_str = input("아이디를 입력해주세요.\n")
real_egoing = "egoing"
real_k8805 = "k8805"
if real_egoing == in_str or real_k8805 == in_str:
  print("Hello!")
else:
  print("Who are you?")
```

### AND
- 아이디는 맞았으나, 비밀번호가 잘못된 경우 반영됨. if 중첩
```
input_id = input("아이디를 입력해주세요.\n")
input_pwd = input("비밀번호를 입력해주세요.\n")
real_id = "egoing"
real_pwd = "11"
if real_id == input_id:
    if real_pwd == input_pwd:                       #id가 맞은 경우 진입
        print("Hello!")
    else:
        print("잘못된 비밀번호입니다")
else:
    print("잘못된 아이디입니다")
```
- 아이디와 비밀번호를 모두 만족할 때 로그인을 시켜주는 프로그램.
```
input_id = input("아이디를 입력해주세요.\n")
input_pwd = input("비밀번호를 입력해주세요.\n")
real_id = "egoing"
real_pwd = "11"
if real_id == input_id and real_pwd == input_pwd:
    print("Hello!")
else:
    print("로그인에 실패했습니다")
```


## [Cheat Sheet](http://overapi.com/python)
- identifiers: 식별자
- variables assignment: 변수에 값을 할당하는 방법
- 대입연산자
- Conditional Statements: 조건문
- etc.


## 주석 (Comment)
부가적인 요소
- (''' '''): 문자열이 됨. 긴 문장을 모두 문자열로 하고싶을 때 사용. enter를 쳐도 사용 가능
- #
``` 
'''
조건문 예제
yj-kim-00
2020
'''
# user input password
input = 33
real_yj-kim-00 = 11
#real_k8805 = "ab"
if real_yj-kim-00 == input:
  print("Hello!, yj-kim-00")
#elif real_k8805 == input:
#  print("Hello!, k8805")
else:
  print("Who are you?")
```

-------------------------------------------------------------------------------
## 컨테이너 (Container)
하나의 리스트 타입 안에 다양한 데이터 타입이 들어갈 수 있다.
```
print(type('egoing'))                             #<class 'str'>
name = 'egoing'
print(name) #egoing
print(type(['egoing', 'leezche', 'graphittie']))  #<class 'list'>
names = ['egoing', 'leezche', 'graphittie']       #[eliments, eliments, eliments]: 컨테이너의 구성요소를 원소라고 한다.
print(names)                                      #['egoing', 'leezche', 'graphittie']
print(names[0])                                   #egoing [index]: 원소의 순번, 색인
print(names[2])                                   #graphittie
egoing = ['programmer', 'seoul', 25, False]
egoing[1] = 'busan'                               #seoul을 busan으로 변경하고 싶을 때
print(egoing) #['programmer', 'busan', 25, False]
```


## 사용 설명서
### 사용 설명서란?
문서(Documentation)
1. 입문서(getting started), 자습서(tutorial)
2. 검색(search), 참조(reference)-자료의 구조 파악

### [Python의 문서 보는 법](https://opentutorials.org/course/1750/9697)과 리스트 심화
[Python 3.x Docs](https://docs.python.org/3/)
```
al = ['A', 'B', 'C', 'D']
print(len(al))              # 4 :len:length
al.append('E')              #리스트의 끝에 추가(append)
print(al)                   #['A', 'B', 'C', 'D', 'E']
del(al[0])                  #del(al[n]) :n번째 원소 제거
print(al)                   #['B', 'C', 'D', 'E']
```


## 반복문**
### While
어떤 조건이 만족되는 동안 반복적으로 실행한다.
```
while False:
    print('Hello world')  #아무것도 실행되지 않음
print('After while')      #After while :반복문 안에 포함되지 않기 때문
```

```
while True:
    print('Hello world')  
print('After while')
```
결과
```
Hello world
Hello world
Hello world
.
.
.
무한히 반복
```

### 반복조건
3번을 반복하기 원할 때
```
i = 0
while i < 3:
    print('Hello world')
    i = i + 1              #i의 값이 1씩 증가
```
결과
```
Hello world
Hello world
Hello world
```

### 활용
프로그램을 만드는 프로그램 만들기

문자열과 숫자를 더하는 것을 불가능.

print('print("Hello world ' + i*9 + '")') 의 결과는 다음과 같다.

TypeError: Can't convert 'int' object to str implicitly

이를 방지하기 위한 방법.
```
i = 0
while i < 10:
    print('print("Hello world '+str(i*9)+'")')  #i를 문자열에서 제외시킨 후 문자열로 변환해야 한다.
    i = i + 1
```
결과
```
print("Hello world 0")
print("Hello world 9")
print("Hello world 18")
print("Hello world 27")
print("Hello world 36")
print("Hello world 45")
print("Hello world 54")
print("Hello world 63")
print("Hello world 72")
print("Hello world 81")
```
과 같이 10번 반복된다.

### 조건문과 반복문의 합체
- 4를 출력하고 싶지 않을 때
```
i = 0
while i < 10:
    if i != 4:
        print(i)
    i = i + 1
```
결과
```
1
2
3
5
6
7
8
9
10
```

- 4만 출력하고 싶을 때
```
i = 0
while i < 10:
    if i == 4:
        print(i)
    i = i + 1
```
결과
```
4
```
- i=4일 때 반복문을 멈추고 싶을 때
```
i = 0
while i < 10:
    if i == 4:
        break
    print(i)
    i = i + 1
print('after while')
```
결과
```
0
1
2
3
after while
```


## 컨테이너와 반복문
### 컨테이너와 반복문의 만남
중복을 없앤다
```
members = ['egoing', 'leezche', 'graphittie']
i = 0
while i < len(members):  #i의 값이 members의 길이보다 작을 때 반복
    print(members[i])
    i = i + 1
```
결과
```
egoing
leezche
graphittie
```

### for문의 등장
atom에서 문단 선택하고 shift+방향키로 선택되는 문장 조절 가능, Ctrl+/ 를 누르면 주석화 됨. 반복하면 취소됨.

for: 반복되어야 하는 것들이 한줄에 포함되어있음. 반면 while의 경우 다른 코드의 영향을 받을 수 있음.
```
members = ['egoing', 'leezche', 'graphittie']
for member in members:                           #컨테이너(리스트) 내부의 요소들을 반복문이 실행될 때 마다 변수(member)에 넣음.
    print(member)
```
결과
```
egoing
leezche
graphitti
```

### for문의 활용
- hello를 5번 반복
```
i=[0,1,2,3,4]
for item in i:
    print('hello')
```
- 반복을 많이 해야하는 경우

range(5): 5번 반복
```
for item in range(5, 11):  #range(a, b): a~b-1 -> 0부터 숫자를 세기 때문
    print(item)
```
결과
```
5
6
7
8
9
10
```

### 로그인 애플리케이션에 투입-복잡해지기 시작
수업에서는 input_output 파일에 있던 2.py container_loop 파일로 가져와 변형했다. ('로그인 애플리케이션에 입력기능 추가하기' 수업)

for문을 통해 로그인 해야하는 사람이 많을 경우 if문만을 사용하기에는 if, elif를 명수만큼 반복해햐 한다는 문제점 해결
```
input_id = input("아이디를 입력해주세요.\n")
members = ['egoing', 'k8805', 'leezche']
for member in members:
    if member == input_id:
        print('Hello!, '+member)
        import sys
        sys.exit()                              #반복문이 끝난 이후에 또 Who are you?가 뜨는 것을 방지. 프로그램 전체 종료
print('Who are you?')
```

-------------------------------------------------------------------------------
## 코드란 무엇인가?

## 함수(function)
### 함수 만들기
a3()
```
def a3():          #함수이름을 a3으로 정의(define)
    print('aaa')   #함수의 본문
a3()               #a3을 호출, 함수의 본문 실행
```
```
aaa
```

### 리턴값
함수를 재사용할 수 있음.

- 표현식(expression). 다음의 함수 모두 같은 결과를 갖는다.
```
print(a3())
print('a'*3)
print('aaa')
```
- print(a3())를 가능하게 하는 방법
```
def a3():
    print('before')
    return 'aaa'  #1. aaa가 함수의 값이 됨. 2. return을 만나면 함수를 종료시킨다.
    print('after')
print(a3())
```
```
before
aaa
```

### 입력값
a를 원하는 갯수 만큼 출력하고자 한다.
```
def a(num):
    return 'a'*num
print(a(3))         #3개
```
```
aaa
```

### 여러개의 입력값
a 뿐만 아니라 어느 문자든 여러개 출력하고 싶다.
```
def make_string(str, num):  #자리수 맞춰줘야함
    return str*num
print(make_string('b', 3))  #str=b, num=3
```
```
bbb
```

### 로그인 애플리케이션 
반복이 발생하는 것을 발견했을 때, 함수로 만들어야 한다.
```
input_id = input("아이디를 입력해주세요.\n")
def login(_id):                                   #login(_id) 함수 정의, id는 파이썬에서 사용 용도가 있기 때문에(파란색) _id로 표현하여 변수로 지정해준다.(주황색)
    members = ['egoing', 'k8805', 'leezche']
    for member in members:
        if member == _id:
            return True
    return False
if login(input_id):
    print('Hello, '+input_id)
else:
    print('Who are you?')
```


## 모듈

## 객체 지향 프로그래밍

## 객체 제작

## 객체와 변수

## 상속

## 클래스 멤버

## Override

## 객체와 모듈

## 다중상속

## 믹스인(Mixin)

## 패키지 매니저
