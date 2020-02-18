# Python (02.18)



#### 객체지향

1. 클래스 : 객체를 표현하는 것
2. 인스턴스 : 실제 메모리에 할당된 것
3. 속성 : 속성 값 (데이터)
4. 메서드 : 행위 함수 



- 클래스

```markdown
carmel case : 첫글자를 제외하고 대문자
pascal case : 첫글자는 전부 대문자
```

> 클래스를 만들어 함수처럼 사용하고 그 안에 들어있는 함수를 .을 통해서 함수호출

```python
class User():   # 클래스에서는 괄호안 내용이 없으면 생략가능 ex) class User:
    username = ''  # class변수이자
    password = ''  # User의 속성
    
    def change_password(self, old, new):   # change_password 는 함수이자 메소드
        if old == self.password:
            self.password = new
            print('완료')
        else:
            print('비번틀림')
```

```python
hyun = User()   # 인스턴스(복제품)

hyun.username = 'hyunsuk'
hyun.password = 'qwer'

hyun.change_password('qwer', 'ssafy')
print(hyun.password)
```



 #### class 내부 여러 함수 생성

```python
class MyList():
    data = []
    
    def append(self, a):
        self.data.append(a)
    def pop(self):
        return self.data.pop()
    def reverse(self):
        self.data.reverse()
    def count(self, a):
        return self.data.count(a) # 요소의 개수
#         return self.data.count(self) # self 전체의 요소개수
    def clear(self):
        self.data.clear()
        
    def __str__(self):
        return 'print빼고 돌려봐'
    def __repr__(self):
        return '내 리스트에는 ' + str(self.data) + ' 이 담겨있다.'
    
hi = MyList()
hi.data.append(1)
# hi.data.pop()
# hi.data.count(1)
hi -> __repr__ 출력
print(hi) -> __str__ 출력
```



