# startcamp day1 (1/15)

### 프로그래밍 3형식

1. 저장
2. 조건(if)
3. 반복(while)



**저장**

> 저장은 save?? 어떤걸 저장했지???

- 글자, 숫자, True, False
- 리스트
- 딕셔너리



**조건**

조건문은 **if**,else,~~elif~~ 로 구성된다.



**반복**

- `while`문을 이용한 반복문

``` python
while n < 3:
    print('출력')
    n=n+1
```

- `for`문을 이용한 반복문

```python
dust = [10,20,30]
for i in dust:
    print(dust)
```

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

### 프로그램 언어 ( 3형식 )

1. 저장
2. 조건(if)
3. 반복(while)



**저장**

- 저장하는 것

1. 숫자 → int
2. 글자 → ' ', " "
3. 참/거짓 → 조건/반복에 사용

ex) 58  숫자   '58' 글자



- 저장 방법

1. 변수 → 박스 하나의 명명

```python
dust=60
dust=85
print(dust)
_result:85
```

```python
print(hello) → hello 변수에 담긴 내용 출력
print('hello') → hello 라는 단어를 출력
```

2. 리스트([ ]) → 박스가 **순서**대로 여러개 붙어있는 개념

```python
dust=[58,40,70]
print(dust[1])
_result:40         → 입력한 수에 해당하는 박스의 값을 도출
```

※컴퓨터는 0부터 수를 셈!

3. 딕셔너리(dict={ }) → 견출지(tagging) 붙인 박스들의 묶음

```python
dust={'영등포구':58, '강남구':40}
print(dust['영등포구'])
_result:58	
```

※key (상자의 이름) , value (상자안의 값)



### 조건문 (if/elif/else)

- if (True/False)

​          print('조건문입니다.')

```python
dust=60     True
if dust>50:
    print('50초과')
else:
    print('50이하')
_result:50초과
dust=40     False
_result:50이하
```



### 반복문

1. while문 → while에 해당하는 조건일 동안 계속 반복

- while True:

​              print('계속해주세요')

```python
n=0
while n<3:
    print('출력')
    n=n+1 ☞ n의 값 새로 덮어씌우기
_result:출력
        출력
        출력
dust=[59,24,102,45,64]
n=0
while n<3:
    print(n)
    n=n+1
_result:59
        24
        102
```

2. for문 → 정해진 박스 내에서의 반복 시 사용

```python
dust=[59,24,102]
for i in dust:
    print(i)
_result:59
        24
        102
```

※ while vs for

while : 조건이 True 인 동안 반복적으로 실행

​             종료조건이 반드시 필요

for : 정해진 범위를 반복하기에

​        종료조건이 필요없음



#### 문제 : 안녕하세요 20번

1)for문

```python
for i in range(20):
  print('안녕하세요')
```

2)while문

```python
a=0
while a<20:
    a=a+1
    print('안녕하세요')
```



*API : 정해진 규칙대로 요청을 하면 그에 상응하는 응답을 해줌

ex) 다른 서버에서 데이터를 가져오는 것, opgg 등

※ 요청(정보를 원하는 사람), 응답(정보를 주는 사람)

### python 함수

1. 내장함수 (**즉각적으로 사용가능**)
    1) print() → 출력
    2) abs() → 절댓값
    3) len('hi') result : 2  → 글자수 

2. 외장함수 (random)
    절차
    1) 수치를 불러옴
    2) 함수에 대입
    ⓐrandom.choice(리스트) → 리스트 안에서 임의의 수를 추출함
    ①. 함수가 포함된 코드를 불러온다.
    **import** random
    ②. 리스트를 만든다.
    menu = [' ', ' ', ' ']
    ③. 함수를 통해 얻은 결과 값을 저장
    choice = random.choice(menu)
    ④. 값을 출력
    print(choice)

  #### 문제 : 메뉴픽

  ```python
  import random
  menu = ['똠양꿍', '쿠우쿠우']
  menu_dict = {'똠양꿍' : '02-573-3857', '쿠우쿠우' : '02-734-2857'}
  pick = random.choice(menu)
  call = menu_dict[pick]
  print(pick, call)
  _result : 쿠우쿠우 02-734-2857
  ```

  ⓑrandom.sample(리스트,개수) → 리스트 안에서 원하는 갯수만큼 임의의 수를 추출

  #### 문제 : 로또번호 6개 출력

  ```python
  import random
  number = range(1,46)
  lotto = random.sample(number,6)
  lotto.sort() ☞ 작은 숫자부터 정렬
  print(lotto)
  _result : [1, 21, 28, 29, 35, 38]
  ```

  