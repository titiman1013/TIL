# startcamp day10 (1.30)

### 알고리즘 1day

- 밤 12시까지 매일 문제 한개씩 당일 제출

```python
import sys
sys.stdin = open("input.txt", "r")
```



#### 알고리즘

> 유한한 단계를 통해 문제를 해결하기 위한 절차나 방법



 **표현방법**

1. 슈더코드

```markdown
정해진 틀이 없다
```

2. 순서도

```markdown
네모형태는 명령에 대한 실행
세모형태는 조건문
```



**좋은 알고리즘이란?**

```markdown
1. 정확성 : 정확하게 동작하는가
2. 작업량 : 적은 연산으로 원하는 결과 창출
3. 메모리 사용량 : 얼마나 적은 메모리를 사용한가
4. 단순성 : 얼마나 단순한가
5. 최적성 : 개선할 여지가 더이상 없이 최적화되었는가
```



시간복잡도

> 실제 걸리는 시간을 측정

- 빅오  표기법을 주로 사용(확인하기)



**배열입력값** 

```python
ARR = [x for x in input()]
: 문자도 들어올거 같을때
ex) 1234ab → '1','2','3','4','a','b'
ARR = [int(x) for x in input()]
: 숫자만 들어올거 같을때
ARR = list(input().split())
: 
ex) 123 abc 46
ARR = list(map(int, input().split()))
```



**for문장**

```python
range(4) → [0, 1, 2, 3]
arr = [0, 10, 20, 3]
for i in range(4)
: 반복횟수가 필요할 경우 주로 사용
for i in range(len(arr))
: 리스트 길이만큼 확실하게 가져다 쓸때
for i in arr
: 리스트에 있는것을 직접 가져다 쓸때
```



#### Tip!

- 같은 반복문을 다시 돌리고 싶었을때는 `continue` 를 통해서 되돌려준다
- 파이썬 자리교환은 그냥 바꾸면 된다

```python
ex) 
list[0],list[1] = list[1],list[0]
```



maxV = val[0]

for i in 



