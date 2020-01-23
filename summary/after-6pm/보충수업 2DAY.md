# 보충수업 2DAY

### 내가 푼 코드

1. 난이도* 1. 개발 카테고리(category)의 갯수를 출력하세요.
   출력예시) 4

```python
1)
len(development['category'])
2)
cate_list = development['category']
count = 0
for cate in cate_list:
    count +=1
print(count)
```

- 강사님풀이

```python
cate_list = development['category'] → 엄연히 category는 key
count = 0
for cate in cate_list:
    count +=1
print(count)
```



2. 난이도** 2. python standard library에 'requests'가 있는지 여부를 True/False로 출력하세요.
   출력예시) False

```python
a = development['language']
b = a['python']
c = b['python standard library']
for i in c:
    if c == 'requests':
        print('True')
else:
    print('False')
```

- 강사님풀이

```python
1)
psl = development['langtuage']['python']['python standard library']
for l in psl:
    if l == 'requests':
        print('True')
    else:
        print('False')
2)
psl = development['langtuage']
print('requests' in psl)  
```

> 접근할때만!!!!!!!!!!!!!!!!!!!!
>
> in 이라는 방법은 시퀀스에 접근할때 사용한다. 
>
> dict에는 불가능 => 사실상 psl.keys()라고 생각하면 된다.

3. 난이도** 3. bts 리더를 출력하세요.
   출력예시) RM

```python
1)
boy = idols['group']['bts']
for name in boy.values():
    if name == 'RM':
        print(name)
2)
boy = idols['group']['bts']['leader']
for name in boy:
    print(name, end="")
3) 예시
boy = idols['group']['bts']['members']
for name in boy:
    print(name)
```

- 강사님풀이

```python
bts_leader = idols['group']['bts']['leader']
print(bts_leader)
```

> list는 리스트 몇번째에 있는지로 접근하고 dict 는 [대괄호]로 접근한다.

4. 난이도*** 4. 개발 언어(language)를 모두 출력하세요.
   출력 예시)  python
                       javascript

```python
1)
com = development['language']
for i in com:
    print(i)
```

- 강사님풀이

```python
l = development['language']
for lang in l.keys():
    print(lang)
```



5.  아이돌 그룹 멤버 모두 출력

```python
indiv = idols['group']
for mem in indiv.values():
    for member in mem['members']:
        print(member)
```

> value값으로 bts와 소녀시대를 불러서 members가 dict안에 들어가 있으므로 [대괄호]로 바로 접근하고 내부 값을 도출

- 강사님풀이

```python
g = idols['group']
for group in g.values():
    for member in group['members']:
        print(member)
```



6.  