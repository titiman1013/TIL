# startcamp day5 (1.21)

#### git 기본

```python
$ git add helloworld.py → sub command 설정
$ git commit -m → '-' short name 옵션
$ git config --global user.name "John" → '--' long name 옵션
```



#### git pull

```python
git pull origin master → git아 origin에 있는 새로운 파일들 master로 가져와
git remote -v → 별명 뭐로 저장되어있는지 확인

※한번에 파일 넘나들기
cd ../python~~
```



### python 활용

```python
a = input → input은 입력상자를 만들고 그 안에 숫자를 넣어도 str으로 인식한다.

※ if 제어문을 적을 때 0의 값은 무조건 False로 인식하고 else값을 도출

※ 수로 범위를 나타낼 때 순차적으로 조건문을 적으면 최대범위를 조건문에 걸 필요가 없지만 순서가 뒤바뀔때에는 최대범위 표기 필요!

※반복문에서는 변수를 새로 입력해 두어도 반복문을 계속 실행

enumerate → 리스트안에 숫자를 또다시 매겨주는 개념?

for문에서 출력값에 []를 통해 value변수를 입력하면 value값만 출력이 가능



```



# 0. dictionary (key 반복)
for key in dict:
    print(key)


# 1. key 반복
for key in dict.keys():
    print(key)
    
    
# 2. value 반복    
for val in dict.values():
    print(val)


# 3. key와 value 반복
for key, val in dict.items():
    print(key, val)

```
A형은 4명입니다. ... O형은 1명입니다.
```