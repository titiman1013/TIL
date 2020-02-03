# Algorithm day3 (20.02.03)



- 평탄화 문제 solve

```markdown
1. 초기값을 0으로 두고 최댓값과 최솟값의 위치를 기억하고 각각의 값들을 +1, -1시켜준다.
2. list로 변수들을 받아서 .sort로 정렬을 해서 이동횟수만큼 앞의값은 1씩 더해주고 뒤의값은 1씩 빼준다.
```



- 2차원배열

**방대한 양의 데이터를 보관하기 위해 사용**

ex) 계란판

1차원배열 : list라고 생각하면 편함

```python
arr = [[0,1,2,3],[4,5,6,7]]
행의 개수(세로의 줄개수), 열의 개수(가로의 줄개수)

선언할때는 [행][열]
```



1. 지그재그 순회2

```python
# 행번호와 열번호가 홀수인지 짝수인지 나눠서 하는 방법
m=4
arr=[list(map(int, input().split())) for i in range(4)]
tmp=[[0]*m for i in range(m)]

print(arr) #=>원본
for i in range(len(arr)):
    for j in range(len(arr[0])):
        if i%2==1:
            tmp[i][j]=arr[i][m-1-j]
            #j가 1씩 감소
        else:
            tmp[i][j]=arr[i][j]
            #j가 1씩 증가
            
print(tmp) #=>지그재그
```



2. 델타를 이용한 2차 배열 탐색

> **기존의 좌표에서 4방향의 인접 배열 요소를 탐색**

※안쪽의 for 문이 더 많이 돌게된다.



3. 전치배열

> 기준값으로 접어서 양쪽이 같은것



<교재 연습문제1>

```python
#델타리스트 이동을 위해 만든 변수
#이동순서 상우하좌
di=[-1, 0, 1, 0] 
dj=[0, 1, 0, -1]

T=int(input())
for tc in range(1, T+1):
    N=int(input())
    arr=[list(map(int, input().split())) for i in range(N)]
    res=0
    tmp=[[0]*N for i in range(N)]
    
    for i in range(N):
        for j in range(N):
            k=arr[i][j]
            SUM=0
            for x in range(4):
                dx=i+di[x]
                dy=j+dj[x]
                if 0<=dx<N and 0<=dy<N:
                    SUM+=abs(k-arr[dx][dy])
            tmp[i][j]=SUM
            #tmp에는 차이의 합이 들어옴
            
    for i in range(4):
        for j in range(4):
            res+=tmp[i][j]
            
print("#{} {} .format(tc,res)")
```



3. 부분집합 생성

> 다음수가 포함이 됐을때 안됐을때의 2경우씩 가지치기로 뻗어져감



4. 비트 연산자(2진수의 연산)

> 부분집합 계산시에 주로 쓰이며 계산속도가 매우 빠르다

```markdown
1. & : and연산
    1011
and 0110
=>  0010 (둘다 1일때만 1)

ex) i&(1<<j):
i의 j번째 비트가 1인지 아닌지 판별하여 리턴

2. | : or연산
    1011
or  0110
=>  1111 (둘중 하나만1이여도 1)

3. not: 연산을 반대값으로 바꿈
not 1011 => 0100

4. << : 자리가 왼쪽으로 한칸씩 밀린다
0001 <<1 => 0010
>  비트연산자에서 자리가 한자리씩 옮겨질때마다 n진수일경우 n씩 곱해진값이 된다!!

5. >> : 자리가 오른쪽으로 한칸씩 밀린다
0001 >>1 => 0000
>  비트연산자에서 자리가 한자리씩 옮겨질때마다 n진수일경우 1/n씩 곱해진값이 된다!!

ex) 원소의 갯수가 n개일때
부분집합의 갯수 : 2^n개
1 <<n : 2^n
```



연습문제2

```python
bit=[0, 0, 0, 0]

for i in range(2):
    bit[0]=i
    for j in range(2):
        bit[1]=j
        for k in range(2):
            bit[2]=k
            for l in range(2):
                bit[3]=l
                print(bit)
```

간단하게


```python
arr=[1, 2, 3]
N=len(arr)

for i in range(1<<N):
    sub=[]
    for j in range(N):
        if i & (1<<j):
            sub.append(arr[j])
    print(sub)
```

> 간단한 방법 그냥 암기하는게 유리



5. 검색(탐색)

> 이진 검색과 해쉬가 가장 속도가 빠름

1) 순차 검색 : 앞에서부터 하나하나 검색

- 정렬이 되어있는 경우 비교적 시간이 줄어든다 (찾는값보다 큰값은 찾지 않음)

2) 이진 검색 : 데이터가 정렬이 되어있어야 사용이 가능하다

- 정중앙을 기준으로 비교한다고 생각하기 (검색을 한번 할때마다 비교할 값이 반으로 줄어듬, 양팔저울을 생각)
- 최대 최소값을 더해 2로 나눈 몫의 번째가 가운데 값이 된다

3) 해쉬 : 