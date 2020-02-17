# Python (02.17)



### 모듈

> 파일의 확장자로 쓰이는 느낌?

- `import` 를 통해서 함수를 불러와서 사용할 수 있다.



### 패키지

> 폴더같은 느낌?

- from 모듈명 import
- from 모듈명 import * 을 하면 해당 모듈내 모든 변수, 함수, 클래스를 가져온다(폴더 끝까지 들어가서 *로 호출해야 한다)

- from 모듈명 import 어트리뷰트 as 를 하면 호출명을 as 뒤의 말로 바꿔서 호출한다(폴더의 끝보다 한칸 덜 들어가서 import로 호출해야 한다)



#### 랜덤함수

```python
import random

lotto = random.sample(range(1, 46), 6) # (범위, 추출갯수)

random.randint(1, 5)
1부터 5사이의 랜덤한 수 하나
```

```python
my_list = [1,2,3,4,5,6,7]
random.shuffle(my_list)
print(my_list)
_result = [4, 2, 7, 5, 1, 6, 3]
# list안의 숫자가 랜덤하게 정렬됨
```

- seed

> 실행 후 바로 난수값을 찾으면 계속 같은 값을 가지게 된다

```python
random.seed(아무숫자)
print(random.random)
# 계속해서 같은 숫자를 output값으로 낸다
```

- datetime

> 날짜와 시간의 조합에 관련된 모듈

```python
from datetime import datetime
datetime.now()
datetime.today()

※ 예쁘게 출력할 때
now.strftime('%y year %m month %d day')
```



### CSV

> `,`  를 기준으로 나눠서 excel처럼 출력

```python
import csv
# url 을 열어서 끄려면
# import requests 도 필요
# from bs4 import BeautifulSoup 도 필요(보기 편하게 하기 위해서)
csvfile = open('csv파일이름.csv', 'w', encoding='utf-9', newline='')
# 한글이 정상적으로 출력되도록 encoding
# newline을 통해 엔터가 쳐져 있는 문제를 해결

※ 내용을 받을때 .text 붙여서 받아줘야 실제 우리가 원하는 정보만 받을 수 있다

csv_writer.writerow() : 한줄만 적어줘~
```



### json

- 대개 dict 안에 필요한 값들을 모두 넣어 한 묶음으로 만들어 사용



### 인터넷 크롤링?

```python
import requests
url = 'url주소'
res = requests.get(url)
user_agent = 인터넷페이지의 f12를 통해 얻은 user-agent 주소
```



### 예외처리



#### 1. 기본 (try, except)

```python
try:
    예외가 발생되지 않으면, except없이 실행이 종료
except 예외(ex. ValueError):
    중간에 예외가 발생하면, 남은 부분을 수행하지 않고, except가 실행
# 모든 예외를 포함할때는 비워둬도 상관없다
```



#### 2. 복수의 예외

```python
try:
    codeblock1
except (예외1, 예외2):
    codeblock2
or
try:
    codeblock1
except 예외1:
    codeblock2
except 예외2:
    codeblock3
```



