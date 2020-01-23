# 보충수업 1DAY

### Q&A

1.  **`!= ` 와 `==` 알아보기**

```python
s = '안녕'
print(s == '안녕')

a = ''
while a != '안녕':
    a = input()
    
a = ''
while not (a == '안녕'):
    a = input()
```



2. **`enumerate`** 란?

```python
for 문은 시퀀스타입만 돌릴 수 있다.
리스트를 튜플로 만들어준다.
굳이 index가 필요한 문에서만 사용한다.
그 외에는 잘 사용을 하지는 않는다.
```



3. `for`  `break`  `else`  란?

```python
for : 정해진 값까지 작업하다 멈춘다.

break : for문을 멈추기 위해 사용
    → break 조건에 걸리면 그 뒤의 작업을 하지 않는다.

else : break가 작동하는지 확인하기 위해 사용이 가능하다.
※ for문에 break나 continue가 없어도 else를 사용하는 것이 가능!!
```



4. dict의 활용

```python
list 에서는 같은 값을 가질 수 있지만
dict 에서는 같은 값을 가질 수 없다.
를 활용해서 수를 세는데 사용할 수 있다.
```



5. len 함수

```python
str을 len함수로 감싸면 글자의 수를 세고
시퀀스를 len함수로 감싸면 시퀀스내의 갯수를 센다.
```



연습문제

```python
development = {
    'category': ['web', 'mobile', 'algorithms', 'deep learning'],
    'language': {
        'python': {
            'python standard library': ['os', 'random', 'webbrowser'],
            'frameworks': {
                'flask': 'micro',
                'django': 'full-functioning'
            },
            'data_science': ['numpy', 'pandas', 'scipy', 'sklearn'],
            'scraping': ['requests', 'bs4'],
        },
        'javascript': {
            'frameworks': ['vue']
        }
    },
    'git': {
       'definition': 'DVCS',
       'services': ['github', 'gitlab', 'bitbucket'],
       'book': 'https://git-scm.com/book/ko/v2'
    }
}

idols = {
    'group': {
        'bts': {
            'leader': 'RM',
            'members': ['진', '슈가', '제이홉', '지민', '뷔', '정국']
        },
        '소녀시대': {
            'leader': '태연',
            'members': ['써니', '티파니', '효연', '유리', '수영', '윤아', '서현']
        },
    },
    'solo': ['아이유', '백예린', '지코']
}
```



1

```
"""
난이도* 1. 개발 카테고리(category)의 갯수를 출력하세요.
출력예시)
4
"""
ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

```

2

```
"""
난이도** 2. python standard library에 'requests'가 있는지 여부를 True/False로 출력하세요.
출력예시)
False
"""
```

3

```
"""
난이도** 3. bts 리더를 출력하세요.
출력예시)
RM
"""
```

4

```
"""
난이도*** 4. 개발 언어(language)를 모두 출력하세요.
출력 예시)
python
java
"""
```





