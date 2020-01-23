# startcamp day6 (1.22)



### 함수란?

1. 함수 선언

```python
def 으로 시작해서 : 으로 끝낸다.
    return 을 통해서 결과값을 전달
```

##### def로 함수이름 정하고 return으로 함수의 수식을 입력하는 개념 → 함수불러서 안에 값 넣으면 내가 계산해서 return으로 내보내줄게~



2. 함수 사용(호출)

```python
func(), func(val1, val2)로 함수를 호출한다. <여기서 함수 이름이 func>
```

ex)

```python
def rectangle(height, width):
    a = height * width
    p = 2 * (height + width)
    print(f'p면적은 {a}, 둘레는 {p}')
    return f'r면적은 {a}, 둘레는 {p}'
a = rectangle(20,30)
print(a)

result_ p면적은 600, 둘레는 100
r면적은 600, 둘레는 100
```

※ 함수 뭐뭐있나 호출어

```python
dir(__builtin__)
```



- 함수 계산 코드짤시 주의사항

```python
def 로 함수를 정의 한 이상 반환하는 방법은 return을 통해서 반환해야지 오류가 생기지 않는다. → print를 통해서 반환하면 None이라는 입력어가 뜬다.

return에 저장을 하면 함수를 변수에 넣고 변수값을 출력하여 값을 낼 수도 있다.

함수안의 매개변수는 항상 순서대로 들어간다.
```



### 기본 인자 값

```python
키워드인자는 마지막에 설정값이 위치해야 한다.
ex) def greeting(name='angel', location):
    return f'{name}은 {location}에 살고 있습니다.'

greeting('devil', 'hell')

result_error!

def greeting(locationm name='angel'):
    return f'{name}은 {location}에 살고 있습니다.'

greeting('devil', 'hell')

result_제대로 출력
```



### *args 와 **kwargs 의 차이

```python
*args : 인자를 꺼내 시퀀스가 있는 리스트로 만들어주는 느낌
**kwargs : 키워드인자의 느낌으로다가 key와 value쌍을 가지고 dict를 만드는 느낌
```

