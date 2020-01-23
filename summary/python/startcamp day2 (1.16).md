# startcamp day2 (1.16)

import webbrowser

webbrowser.open('주소')

webbrowser.open_new('주소')

webbrowser.open_new_tab('주소')

```python
import webbrowser
url='https://search.naver.com/search.naver?query='
>>> keywords=['아이유','박신혜','위너','ITZY','BTS']
for keyword in keywords:
	webbrowser.open(url+keyword)
```

vs code : 코드 에디터

파이참 : ID통합개발환경



1. **crawling**

#### vs code 명령어

```python
python hello.py → 명령어들 실행문
ls=list
pip install requests → 빨간줄 뜰 때 공구상자 가져오기
res=request
pip install bs4 → 터미널 정리할 때(파이썬 시점)
from bs4 import BeautifulSoup → bs4 안에있는 BeautifulSoup 가져와
.select → 이쁜거 다 뽑아줘
.select_one → 이쁜거 하나만 뽑아줘
if __name__ == '__main__':
    app.run(debug=True)      →  자동으로 실행
※도구는 도구끼리 code를 모아서 묶는게 보기 좋음
```

#### 참고

```python
import requests
requests.get('주소')
requests.get('주소').text → text만 가져오기
requests.get('주소').status_code → code만 가져오기
웹브라우저 → 우클릭 → 검사 → 우클릭 → copy selector
```

#### 실적용 코스피찾기

```python
import requests → requests 상자 가져와 
from bs4 import BeautifulSoup → bs4에서 beautifulsoup 가져와

sise_url='https://finance.naver.com/sise/' → 복잡한거 간략하게 설정

res=requests.get(sise_url).text 
soup=BeautifulSoup(res, 'html.parser') → 간략화
#KOSPI_now

kospi=soup.select_one('#KOSPI_now') → 아이디가 KOSPI_now인거 하나 가져와
print(kospi.text) → text만 출력해
```




2. **HTML**

#### 명령어

```python
F12 → 개발자도구
<ol> → 숫자표시
<ul> → 점점점표시
<a> → 하이퍼텍스트 → 닻의 느낌(anchor)
<a href="주소"> → 닻을 건 좌표
```

#### HTML 만들기

```python
<!-- 여기는 주석입니다. -->
<!DOCTYPE html>
<html>
    <head>
        <title>여기는 html실습을 위한 페이지입니다.</title>
    </head>
    <body>
        <h1>HTML!!!</h1>
        <h2>뭘봐</h2>
        <h3>그만 나가지?</h3>

        <ul>
            <li>안녕하세요</li>
            <li>반갑습니다</li>
        </ul>

        <ol>
            <li>첫번째</li>
            <li>두번째</li>
        </ol>

        <a href="http://www.naver.com">네이버</a>

    </body>
</html>
```



3. **Flask(간단한 서버 구축)**

```python
pip install flask
flask run FLASK_APP=hello.py
cd 폴더명 → 폴더안으로 들어갈때 쓰는 명령어
cd .. → 폴더 밖으로 나갈때
set FLASK_APP=hello.py → flask야 내 파일 등록해줭
`! enter → html 작성 기본셋팅
```





#### 총합적으로 'hello.py'에 들어간 것


```python
from flask import Flask, escape, request, render_template
import random

app = Flask(__name__)

@app.route('/welcome')
def welcome():
    return '반갑습니다'

@app.route('/html_tag')
def html_tag():
    return """
    <h1>헤딩1번입니다.</h1>
    <ul>
        <li>안녕하세요.</li>
    </ul>
    <ol>
        <li>안녕못해요.</li>
    </ol>
    """

@app.route('/first')
def first():
    return render_template('hello.html')

@app.route('/name/<string:name>')
def name(name):
    return render_template('name.html', html_name=name)

@app.route('/cube/<int:num>')
def cube(num):
    cube_num=num**3
    return render_template('cube.html',html_num=num, html_cube_num=cube_num)

@app.route('/lunch')
def lunch():
    menu=['한우타다끼','육회비빔밥','육사시미','삼겹살','상하이스파이시버거']
    menu_dict={
        '한우타다끼': 'https://post-phinf.pstatic.net/MjAxNzA0MDFfMTU1/MDAxNDkxMDMwMDg2OTc2.a6chQUnag48HwvcsaQDvd8c_Wh5OFIksezx9885B1okg.kJXG5tCoUOOPK683dAhD08tl2NTGhDy2YqwHVdPyCFEg.JPEG/%EC%83%81%EB%AC%B4%EC%A7%80%EA%B5%AC%EC%88%A0%EC%A7%91IMG_9520.JPG?type=w1200',
        '육회비빔밥': 'https://imagescdn.gettyimagesbank.com/500/201708/jv10931654.jpg',
        '육사시미': 'https://mblogthumb-phinf.pstatic.net/MjAxODA1MjZfMjQ5/MDAxNTI3Mjk1MzkxNTEz.5pqDQ-MoKkn810m9yOYZUEv4qbBF9Zel6j3_n8zh11gg.bTAYkv_fC6lp8nx56HoPx8ItcIeEbG5TKYq0mPnoD_wg.JPEG.zadoz/image_6854317561527292242783.jpg?type=w800',
        '삼겹살': 'http://recipe1.ezmember.co.kr/cache/recipe/2018/04/17/eb70d87623d79fe27daeb9cc929b185e1.jpg',
        '상하이스파이시버거': 'http://pds23.egloos.com/pds/201209/11/18/d0050518_504f40ed3e40c.jpg',
    }
    pick=random.choice(menu)
    img=menu_dict[pick]
    return render_template('lunch.html',pick=pick,img=img)

@app.route('/movies')
def movies():
    movies=['해치지않아', '닥터 두리틀', '백두산']
    return render_template('movies.html',movies=movies)

@app.route('/ping')
def ping():
    return render_template('ping.html')

@app.route('/pong')
def pong():
    location=request.args.get('location')
    return render_template('pong.html',location=location)

@app.route('/hit')
def hit():
    return render_template('hit.html')

@app.route('/result')
def result():
    punch=request.args.get('punch')
    dae=['1대','2대','3대','4대','5대']
    dae_dict={
        '1대': 'https://mblogthumb-phinf.pstatic.net/MjAxODA5MDRfMTM1/MDAxNTM1OTkyNDE0MDYy.OOAHv9kNzUfCy4nR6xbA3OGa4_tjupZI464iKOpPXWkg.WvqG25wOM7tZI6xiPcRY9jkQXFjtX7UZ5B7GBmnloz4g.JPEG.utopia4640/19_%EB%AA%87%EB%8C%80_%EB%A7%9E%EC%9D%84%EB%9E%98.jpg?type=w800',
        '2대': 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQQ_0iBf7JGdwOLhbA32-eeWLljcE-v9B7-NFmqfONkFquZQBWuLg&s',
        '3대': 'http://mblogthumb3.phinf.naver.net/MjAxOTAxMDFfMTQz/MDAxNTQ2MzQ0MTE4NTA5.cDLbnpR0wnF2NYEi9OIyuTSTPPcxl1k8F3Qo5QeNW4Mg.u1EUpdMY2b6-GntYaYdEXWdcYc5YvhJkhp2K4D5SY9Mg.JPEG.utopia4640/%ED%91%9C%EC%A0%95_%EC%99%9C_%EA%B7%B8%EB%9E%98_%EC%9D%B8%EC%83%81_%EC%95%88%ED%8E%B4.jpg?type=w800',
        '4대': 'http://mblogthumb2.phinf.naver.net/MjAxOTAxMDFfNjUg/MDAxNTQ2Mjc5MzczNzk2.RnIQid9mydSzM2Dju8pLCiNKnkQYUZizNY6vDmzyNe8g._qghHC0Zq67uSXD2AU_KPdlQi-WEkT1Ey5EVA-KGIPwg.JPEG.utopia4640/%ED%9A%8C%EC%B4%88%EB%A6%AC_%EA%B0%80%EC%A0%B8%EC%99%80_%ED%9A%8C%EC%B4%88%EB%A6%AC.jpg?type=w800',
        '5대': 'http://mblogthumb2.phinf.naver.net/MjAxODEyMzFfMTQ1/MDAxNTQ2MjUzNzgyNjUz.Fl_OKpEEMkCkyuyV_w-tgFgtuLgWpcgRqLGzSvNHigQg.DZcmDtbV3-OCXLmr69FEIaDm2L6oghYXetVrNLliddkg.PNG.utopia4640/30.75_%ED%95%9C%EA%B3%84%EC%9E%84%EB%B0%95_%EB%B9%A1%EC%B9%A8.png?type=w800',
    }
    select=request.args.get('dae')
    rg=dae_dict[select]
    return render_template('result.html',punch=punch,rg=rg)

@app.route('/')
def hello():
    name=request.args.get("name","World")
    return f'안녕하세요, {escape(name)}!'

if __name__ == '__main__':
    app.run(debug=True)
```

#### html에 들어간것

```python
-hit.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <h1>너 나한테 몇 대 맞을래?</h1>
    <form action='/result'>
        몇 대? : <input name='punch'>
        <input type='submit'>
    <img src ='https://image.fmkorea.com/files/attach/new/20160814/486616/35940164/437454578/bedd0ee2f2469632497ae1755b2839a5.jpg'}} width='500' height='500'>
    </form>
        
</body>
</html>
```

```python
-result.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <h1>당신이 맞을 횟수</h1>
    {{punch}}
    <h2>{{select}}</h2>
    <img src={{rg}} width='500' height='500'>
    
</body>
</html>
```

```python
-lunch.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <h1>오늘의 추천메뉴</h1>
    <h2>{{pick}}</h2>    
    <img src={{img}} width='500' height='500'>
</body>
</html>
```

```python
-movies.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <h1>이번주 상영영화</h1>
    {{movies}}
    {% for movie in movies %}
        <li>{{movie}}</li>
    {% endfor %}
</body>
</html>
```

