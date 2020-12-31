# 1日目

動画

<https://youtu.be/XjAv7UJFbgM>

## アナコンダのインストール

<https://www.anaconda.com/products/individual>

## オンラインエディタ

<https://paiza.io>

## 初めてのプログラミング

Spyderに以下を入力して実行してみましょう。

```py
print("Hello")
```

## プログラミングで出来るちょっとすごいこと

※以下は今できるようになる必要はありません。ふーんと思ってもらえればOKです。

### 画像自動作成

動画を参考に、Spyderエディタに直接コピペして実行してみましょう。

```py
import random

from PIL import Image, ImageDraw



def generate_image(file_name):
    # ランダムな色を生成 Red, Green, Blue
    r = random.randint(0, 251)
    g = random.randint(0, 251)
    b = random.randint(0, 251)
    
    mode = "RGB"
    size = (300, 300)
    color = (r, g, b)

    image = Image.new(mode, size, color)
    draw = ImageDraw.Draw(image)
    draw.text((size[0]/2 - 20, size[1]/2 - 20), file_name)
    
    image.save("./" + file_name + ".png")
    

    
for i in range(10):
    generate_image("image" + str(i))
```

### リアルタイム株価取得

```py
import requests

URL = "https://stocks.finance.yahoo.co.jp/stocks/detail/?code=7203.T"
res = requests.get(URL)
lines = res.content.decode("utf-8").split("\n")
line = [l for l in lines if "stoksPrice" in l][1]
print(line[line.find(">")+1:-5])
```

