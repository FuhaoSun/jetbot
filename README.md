# JetBot
### 株式会社アフレルで夏季インターンシップに参加し、JetBotに関する経験を共有しています。<br>
こちらはjetbotに関する情報でございます。<br>
写真はNvidia公式サイトもしくはGithubサイトより。<br>
基本的には公式GitHubサイトのステップに従えば問題ないと思います。<br>
>参考サイト：<br>
>英語（公式サイト）：https://github.com/NVIDIA-AI-IOT/jetbot/wiki<br>
>日本語：https://www.ogis-ri.co.jp/otc/hiroba/technical/lets-try-jetbot/part1.html<br>
>中国語：https://www.ncnynl.com/archives/201904/2927.html<br>
## ⅠJetBotの組立について
JetBot公式wikiを読むことをお勧めします: [JetBot Wiki](https://github.com/NVIDIA-AI-IOT/jetbot/wiki).<br>
##### ハードウェアのセットアップ<br>
ジャンパワイヤーは片側がオスのものを使用します。もう一方は配線を剥いてはんだ付けしますので、両側がソケットになっている必要はありません。<br>
便宜上、ジャンパワイヤーは異なる色を使用しています。<br>
今度は赤と黒です。（左赤右黒）<br>
#<div align=center><img width="320" height="480" src="https://github.com/FuhaoSun/jetbot/raw/master/photos/1.jpg"/></div><br>
##### 2.ネジは25mm長のM3を使い、ナットで固定します。<br>
##### 3.右向きマイクロUSBケーブルカットして、配線を剥いて。赤と黒だけ使いますので、緑と白は不要。<br>
##### 4.PiOLEDディスプレイがJetson Nano本体をはんだで固定のは難しいです。はんだ使う時ディスプレイの損傷の可能性あるので、要注意。<br>
#<div align=center><img width="480" height="320" src="https://github.com/FuhaoSun/jetbot/raw/master/photos/2.jpg"/></div><br>
##### 5.Wi-Fiカードは任意ですが、今度は無線LANアダプタを使用しています。（型番BUFFALO　WLI-UC-GNM2S）<br>
##### 6.注意点：JetBotのOSイメージは通常版が64GBを超えているため128GB以上のmicroSDカードが必要になります。（64GBのmicroSDカードでも収まる63GBの縮小版イメージもありますが、後述の教師データの収集等を考えると、大きなサイズのmicroSDカードを準備することをお勧めします）<br>
##### 7.公式Wikiのサンプル画像に間違っている箇所があります。

#<div align=center><img width="450" height="300" src="https://github.com/FuhaoSun/jetbot/raw/master/photos/3.jpg"/></div>
上記の画像では、左右のモーターの赤と黒のワイヤーが実際に裏返されています。<br>
これは損傷の原因にはなりませんが、モーターは逆回転します。それらを正しい方向に反転させてください。<br>
##### 8.カメラのケーブル挿入方向について<br>
公式wikiも書きませんですが、もし間違えるなら、画像ないと思います。<br>
こちらは写真付き：<br>
#<div align=center><img width="320" height="480" src="https://github.com/FuhaoSun/jetbot/raw/master/photos/4.jpg"/></div>
##### 9.溶接時間は長すぎてはいけません。さもないと部品が焼けてしまいます。<br>
別ネタですが、私は小学校の時、はんだを使い始めました。いくつかのロボットを壊しました。<br>
## Ⅱサンプルコードの実行について
##### 1.テスト用コード
`NoteBook`を開けます、`Kernel`を`Python3`を選択して、`Run All Cells`をクリックします。
```Python
/*前へ進む1秒、そして止まる*/
from jetbot import Robot
import time
robot = Robot()
robot.set_motors(0.3,0.3)
time.sleep(1.0)
robot.stop()
```
##### 2.共通手順
>* Jetbot電源ON<br>
>* http://<jetbot_ip_address>:8888に移動してロボットに接続します。<br>
		(IPアドレスはロボットのディスプレイに表示されます。<br>
>* `Kernel`➡`Shutdown All Kernels...`を選択して、実行中の他のすべての`Notebook`を閉じます。<br>
>* 事前トレーニング済みのモデルをフォルダーにアップロードします。（例３は1個、例４は2個）。<br>
>* `Notebook`を開いて、操作をフォローします。<br>
##### 3.サンプルコードの実行について
①例１：基本的には、問題ありません。<br>
②ゲームコントローラー必要です。<br>
PS4コントローラーの場合は、index=0<br>
③<br>
④このサンプルコード（オブジェクトフォロー）では、設定されるフォロー対象三つあります。（人、犬、コップ）わが会社の空間ちょっと狭いから、人と犬は無理ですね。今度は「いろはす天然水」を使う。効果まあまあです。<br>
##### 4.例３と例４の読み込み時間がかなり長いです（2分程度）。エラーではない。
