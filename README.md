## Python
파이썬(영어: Python)은 1991년 프로그래머인 귀도 반 로섬(Guido van Rossum)이 발표한 고급 프로그래밍 언어로, 플랫폼에 독립적이며 인터프리터식, 객체지향적, 동적 타이핑(dynamically typed) 대화형 언어이다. 파이썬이라는 이름은 귀도가 좋아하는 코미디 〈Monty Python's Flying Circus〉에서 따온 것이다.
파이썬은 비영리의 파이썬 소프트웨어 재단이 관리하는 개방형, 공동체 기반 개발 모델을 가지고 있다. C언어로 구현된 Cython 구현이 사실상의 표준이다.
참고: [위키백과, 파이썬](https://ko.wikipedia.org/wiki/%ED%8C%8C%EC%9D%B4%EC%8D%AC)


python 공부 내용 정리. 참고:[생활코딩](https://opentutorials.org/course/1)

2020.04.22까지 정리내용


### Python 실행
cmd 입력: window+r
1. 대화형 모드 실행: 복잡한 프로그램 작성에 어려움.
cmd 창에 직접적으로 실행
```
python
print('hello world')
Ctrl+c  #작업을 끝냄 
```
2. 파일 모드 실행
메모장 사용, 저장시 .py파일로 저장, 모든파일, utf-8
```
저장 위치 복붙 #파일탐색기에서 해당 파일 우클릭 후 속성 참고ex)C:\Users\hikyj\OneDrive\text\python_ruby
```


### 수와 계산
숫자를 프로그래밍적으로 표현하는 방법(문법)
1. 사칙연산
```
print(10+5)
print(10-5)
print(10*5)
print(10/5)
```
2. 살짝 복잡한 계산
정수와 실수 인식됨.
```
import math               #가져옴/수학적계산
print (math. ceil(2.2))   #올림->3
print (math. floor(2.7))  #내림->2
print (math. pow(2,10))   #2의 10승->1024
print (math. pi)          #원주율 출력->3.141592653589793
```


### 문자와 데이터 타입
1. 문자의 표현
문자열(string)
```
print('Hello')          #Hello
print("Hello")          #Hello
print("Hello 'world'")  #Hello 'world'
print('Hello "world"'   #Hello "world"
```
("''") or ('""')가능. 문자열의 시작과 끝을 나타내기 때문.(문자열로 인식하기 시작하기 때문.)
('''') or ("""")의 경우 syntax error 발생

2. 문자열의 제어(문자연산)
```
print('Hello '+'world') #문자열을 더함. Hello world
print('Hello '*3)       #문자열을 숫자 만큼 반복. Hello Hello Hello 
print('Hello'[0])       #H  :0 번째 문자를 출력
print('Hello'[1])       #e  :1 번째 문자를 출력
print('Hello'[2])       #l  :2 번째 문자를 출력
```
문자연산에는 +, * 만 존재

3. 문자열의 제어2
```
print('hello world'.capitalize())                     #Hello world  :첫 번째 문자만 대문자로 표시
print('hello world'.upper())                          #HELLO WORLD  :모든 문자를 대문자로 표시
print('hello world'.__len__())                        #11 :문자의 개수
print(len('hello world'))                             #11 :문자의 개수
print('Hello world'.replace('world', 'programming'))  #Hello programming  :'world'를 'programming'으로 변환
```
replace('a', 'b'): 텍스트 편집기능(find and replace) 바꾸기 원하는 텍스트를 찾아 바꿔줌

4. 특수한 문자들
escape: \
new line: \n
tap: \t
alert: \a
```
print("egoing's \"tutorial\"")  #egoing's "tutorial" :' 또는 " 앞에 붙어 일반문자로 해석하기 위해 사용
print("\\")                     #\ :\를 화면에 표시하고 싶을 때
print("Hello\nworld")           # :줄바꿈
print("Hello\t\tworld")         # Hello       world:tap 2번
print("\a")                     #   :경고음 울림
print('Hello\nworld')           # :""과''의 역할이 거의 동일
```
print("\") ->오류, 닫히지 않은 문자로 인식

5. 문자와 숫자를 통해서 알아보는 데이터 타입
10과 "10"은 다르다
```
print(10+5)       #15 :산술연산
print("10"+"5")   #105 :문자연산
```


### 변수
1. 변수의 기본 문법
변수=숫자, 변수=문자열
```
x=10
y=5
print(x+y)                #15
 
title = "python"
print("Title is "+title)  #Title is python
```

2. 문자열에서 변수의 사용
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

3. 수 계산에서의 변수의 사용
다음은 장학재단이 한명의 학생에서 1년에 a만원을 후원한다고 가정할 때, c명의 후원자가 돈을 얼만큼 내야 후원을 받을 수 있는 학생수가 b명이 되는지를 계산하는 과정이다.

이는 계산 후 대입을 하는 방식으로, 공식을 만들고 변수를 사용하여 해당 변수의 대입값에 혼동이 오지 않도록 한다.->대수학
```
donation = 200  #a
student = 10    #b
sponsor = 100   #c
print((donation*student)/sponsor) #20
```
따라서 후원자 1인당 20만원을 부담해야한다.


### 개발도구
편리성이 증가할수록 안전하게 사용할 수 있는 훈력과 교육을 요구하고, 위험도가 증가한다.

-ATOM: 편집기
-[IDE](https://www.jetbrains.com/pycharm/): 통합 개발 도구->데이타 베이스 제어, 소스코드를 제어하는 버전관리, 편집기


### 비교와 블리언(Boolean)
숫자의 대소관계
-숫자, 문자: 많은 값들로 이루어져있는 데이터 형식 
-블리언: 조건문, 반복문의 핵심적 역할을 하는 도구, 참과 거짓 두개의 값으로만 이루어짐.

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


### 조건문(Conditional Statements)
1. 기본문법 (조건이 없는 경우)
```
if False:
    print("code1")
    print("code2")  #조건문의 끝을 구분하는 기준: 공백(들여쓰기)을 가지고 있는 명령문을 같은 그룹으로 인식
print("code3")      #if문 바깥에 존재
```
결과: code3
-true->실행
-false->실행되지 않음

2. 조건문의 활용
로그인 프로그램-동등비교연산자 
```
input = 11
real = 11
if real == input:
    print("Hello!")
```
