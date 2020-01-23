# startcamp day4 (1.20)

1. Slack : 급하고 간단한거
2. Trello : 약간 중요한거나 간직하고 싶은거



cd python-student

jupyter notebook



#### git 명령어

```text
add : 커밋할 목록에 추가

commit : 커밋(create a snapshot) 만들기

push : 현재까지의 역사(commits)가 기록되어 있는 곳에 새로 생성한 커밋들 반영하기

ls : 파일 뭐로 썼나 확인,파일 뭐있나 확인
ls -a : 만약 .git이 있으면 secret 파일
q : 긴급탈출~!
※README 꼭꼭 만들어주기
```



#### git 저장

```python
git init → git야 이거 관리해줘
touch '이름' → 새로운 파일을 만드는 명령어
.gitignore → 얘네는 무시하고 올려줘
ls -a → list를 보여줌
1. git add . → 파일을 임시저장
git status → 상태확인
2. git commit -m "파일설명,이름" → 파일을 완전 저장
ex) git config -m "01_python_intro 추가"
3. git remote add origin "어찌고 저찌고, 대개 주소" 복붙 → 저장할곳 입력
4. git push origin master → 올려줘
5. git log → 기록 확인
※각각올리고 싶을때
>git add '폴더명'/'파일명'
git diff → 파일간의 차이 알려줘
```



#### jupyter 켜기

```python
git 실행 → pip install notebook → jupyter notebook 
```



#### jupyter 사용법

```python
하나의 칸을 cell이라 명명하고 ctrl+enter로 실행
파란색 : commend mode → cell단위로 움직임이 가능
초록색 : edit mode → 수정이 가능
ctrl+enter : cell 실행 후 그 cell에 머무름
shift+enter : 그 다음 cell로 감
alt+enter : 다음에 새로운 cell을 만듬
cell 삭제 : dd
```



#### python 활용

```python
주석(docstring) : # , '''입력값'''
docstring 확인 : mys.__doc__
print('''텍스트''') → 여러줄로 인식

print('123');print('abc')
_result : 123               → 이것보다는 print
          abc                  두번사용하여 출력하기

EOL error : end of line error → 줄 끝에 에러
백슬래쉬사용 → 문장을 붙여주지만 사용을 지양
			 python언어 문법을 escape! 
대괄호 같은 것들은 엔터를 쳐도 출력에러 ㄴㄴ

x와 y의 값을 바꾸기
	print(x, y)         1 2
	temp = x
	x = y            →  
	y = temp
	print(x, y)         2 1

※jupyter notebook 에서는 마지막값을 print()씌워 도출

round(3.4 - 3.14, 2) → 소숫점 둘째자리에서 반올림해줘

소수점 숫자 비교:
    import math          →   참/거짓으로 판단
    math.isclose(a, b)
    
print(a.real)          → 실수부 
print(a.imag)          → 허수부
print(a.conjugate())   → 켤레복소수

divmod(5,2) → (몫, 나머지)
	a, b = divmod(5,2) 
	print(a,b) →  2 1

단축평가 (or 은 반대)
print(3 and 5) # T1 T2 => T2 앞에 있는 값이 T면 뒤에 있는 T값을 도출
print(3 and 0) # T1 F2 => F2 둘 중 하나가 아닐때 앞이 참이면 뒤의 거짓값을 도출
print(0 and 3) # F1 F2 => F1 둘 중 하나가 아닐때 앞이 거짓이면 앞의 값을 바로 도출
print(0 and 0) # F1 F2 => F1 둘 중 하나가 아닐때 앞이 거짓이면 앞의 값을 바로 도출

계산에서의 우선순위

암시적 형변환 : 서로 다른 개념의 계산이 일어나면 더 큰 개념의 type으로 변환
명시적 형변환 : 사용자가 직접 type을 바꿔줘야 함

item → 리스트로 묶어서 튜플의 형태로 보여줌
```



#### python 진수

```python
binary_number = 0b10
octal_number = 0o10
decimal_number = 10
hex_number = 0x10
print(binary_number)
print(octal_number)
print(decimal_number)
print(hex_number)
_result:2
		8
		10
		16
```

