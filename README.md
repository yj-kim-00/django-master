## Python

python 공부 내용 정리-[생활코딩](https://opentutorials.org/course/1) 참고

### python 실행
cmd 입력: window+r
1. 대화형 모드 실행: 복잡한 프로그램 작성에 어려움.
cmd 창에 직접적으로 실행
```
python
print('hello world')
Ctrl+c #작업을 끝냄 
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
import math #가져옴/수학적계산
print (math. ceil(2.2)) #올림
print (math. floor(2.7)) #내림
print (math. pow(2,10)) #2의 10승
print (math. pi) #원주율 출력
```
