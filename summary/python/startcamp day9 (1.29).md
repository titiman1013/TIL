# startcamp day9 (1.29)



#### 1. map(function, iterable)

- Iterable한 객체(반복가능한 변수 ex.list등)의 모든 요소에 함수에(function) 적용한 후 결과를 돌려준다.

```python
#list comprehension
result = [str(number) for number in numbers]
print(''.join(result))
#map
result = map(str, numbers)
print(''.join(result))
```



#### 2. zip(*iterables)

- 복수의 iterable 객체를 모아 튜플의 모음으로 반환한다.

```python
girls = ['jane', 'iu', 'mary']
boys = ['justin', 'david', 'kim']

input_code : {girl: boy for girl,boy in zip(girls, boys)}

_result : {'jane': 'justin', 'iu': 'david', 'mary': 'kim'}
```

> 1대1 매칭을 시킬 때 편리하다



#### 3. filter(function, iterable)

- iterable에서 function의 반환된 결과가 `True` 인 것들만 구성하여 반환한다.

```python
def odd(num):
    if num % 2:
        return True
    else:
        return False
    # 나머지가 1 => 홀수 => True
    # 나머지가 0 => 짝수 => False
#    return num % 2
numbers = [1,2,3,4,5,6,7,8,9,10]
result = list(filter(odd, numbers))
print(result)

_result: [1, 3, 5, 7, 9]
```



