# Algorithm (02.12)



## stack1

> 특징 : 후입선출

>  ex) 1,2,3 순으로 자료를 삽입한 후 꺼내면 역순으로 3,2,1순으로 꺼낸다



- 주로 pop 과 append 로 list에 저장
- 함수안에 함수가 존재할 때 마지막 함수가 끝났을 때 마지막 함수를 호출했던 함수로 돌아간다



#### DP(Dynamic Programming)

```python
def fibo(n): # DP를 이용한 피보나치(반복)
    memo[0] = 0
    memo[1] = 1
    for i in range(2, n+1):
        memo[i] = memo[i-1] + memo[i-2]
    return memo[n]

N = int(input())
memo = [-1] * (N+1)

print('피보나치 결과:', fibo(N))
```



#### DFS(깊이우선탐색)

1. 전체값을 Fasle로 두고 방문을 한곳을 True 로 바꿔준다
2. False 인 곳으로 이동을 하면 전에 방문했던 곳을 stack에 append해준다
3. 반복
4. Fasle인 곳이 없다면 stack의 마지막에쌓인 것을 pop하여 그 위치로 돌아간다

   5-1. stack안의 값이 없어질때까지 반복하면 모든 곳을 방문한 것이다

   5-2. 만약 모든 장소가 True라면 모든 곳을 방문한 것이다