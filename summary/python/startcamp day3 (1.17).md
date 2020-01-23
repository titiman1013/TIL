# startcamp day3 (1.17)

javert2_bot

f string -> 문자안에 변수입력

webhook~ anchor



#### app.py로 만든코드

```python
from flask import Flask, escape, request, render_template
import requests
import random

app = Flask(__name__)

token = '1014845668:AAEy1mESv1h7_9D0M4O9sh27qYpwzF1Ge-A'
url = f'https://api.telegram.org/bot{token}/'
my_id = 1033892853
ngrok_url = 'https://a9c97714.ngrok.io'
papago_api_id = '42ya4AhV3xuD6taXfima'
papago_api_secret = 'SBQW9VHEvK'

@app.route('/')
def hello():
    webhook = f'{url}setWebhook?url={ngrok_url}/telegram'
    return webhook

@app.route('/write')
def write():
    return render_template('write.html')

@app.route('/send')
def send():
    msg = request.args.get('msg')
    msg_url = f'{url}sendmessage?chat_id={my_id}&text={msg}'
    res = requests.get(msg_url)
    print(res.text)
    return render_template('send.html', msg=msg)

@app.route('/telegram', methods=['POST'])
def telegram():
    #print(request.get_json())
    res = request.get_json()
    user_id = res.get('message').get('from').get('id')
    user_msg = res.get('message').get('text')
    #print(user_id, user_msg)

    if user_msg == '노예야':
        return_msg = '하잇 고슈진사마!'
    
    elif user_msg == '오늘 점심 뭐냐?':
        menu=['한우타다끼', '육사시미', '육회비빔밥']
        return_msg = random.choice(menu)
    
    elif user_msg == '너 날 위해 죽어줄 수 있어?':
        return_msg = '당연하죠 주인님'
    
    elif user_msg == '이번주 로또번호 추천해봐':
        number = range(1,46)
        lotto = random.sample(number,6)
        lotto.sort()
        return_msg = str(lotto) + '일거 같습니다 주인님'

    elif user_msg == '반말하냐?':
        return_msg = '죄송합니다... ㅠㅠ'

    elif user_msg == '아니면 뒤져':
        return_msg = '그건 너무한거 같습니다 주인님 ㅠ^ㅠ'

    elif user_msg == '나 왔다 인사 오지게 박아봐라':
        come = '어서오십시오 주인님'
        for i in range(4) :
            return_msg = come
            send_url = f'{url}sendMessage?chat_id={user_id}&text={return_msg}'
            requests.get(send_url)
    elif user_msg == '미쳤냐?':
        return_msg = '죄송합니다 너무 더워 더위를 먹은거 같습니다 ㅠ'

    elif user_msg == '오냐':
        return_msg = '감사합니다 주인님'

    elif user_msg[0:4] == '번역해 ':
        before = user_msg[4:]

        headers = {
            'X-Naver-Client-Id': papago_api_id,
            'X-Naver-Client-Secret': papago_api_secret
        }
        papago_url = 'https://openapi.naver.com/v1/papago/n2mt'

        data = {'source': 'ko',
                'target': 'en',
                'text': before
                }

        res = requests.post(papago_url, headers=headers, data=data)
        before = (res.json().get('message').get('result').get('translatedText'))
        return_msg = before

    else :
        return_msg = '잘 못알아 먹겠습니다 주인님'

    send_url = f'{url}sendMessage?chat_id={user_id}&text={return_msg}'
    requests.get(send_url)

    return '',200

if __name__ == '__main__':
    app.run(debug=True)
```

