# JetBot
### 株式会社アフレルで夏季インターンシップに参加し、JetBotに関する経験を共有しています。<br>
こちらはjetbotに関する情報でございます。<br>
写真はNvidia公式サイトもしくはGithubサイトより。<br>
基本的には公式GitHubサイトのステップに従えば問題ないと思います。<br>
>参考サイト：<br>
>英語（公式サイト）：https://github.com/NVIDIA-AI-IOT/jetbot/wiki<br>
>日本語：https://www.ogis-ri.co.jp/otc/hiroba/technical/lets-try-jetbot/part1.html<br>
>中国語：https://www.ncnynl.com/archives/201904/2927.html<br>
## 一、	jetbotの組立について
Jetbot公式wikiを読むことをお勧めします: [JetBot Wiki](https://github.com/NVIDIA-AI-IOT/jetbot/wiki).<br>
##### 1.ハードウェアのセットアップ<br>
ジャンパワイヤーは片側がオスのものを使用します。もう一方は配線を剥いてはんだ付けしますので、両側がソケットになっている必要はありません。<br>
便宜上、ジャンパワイヤーは異なる色を使用しています。<br>
今度は赤と黒です。（左赤右黒）<br>
![](https://github.com/FuhaoSun/jetbot/raw/master/photos/1.jpg)<br>
##### 2.ネジは25mm長のM3を使い、ナットで固定します。<br>
##### 3.右向きマイクロUSBケーブルカットして、配線を剥いて。赤と黒だけ使いますので、緑と白は不要。<br>
##### 4.PiOLEDディスプレイがJetson Nano本体をはんだで固定のは難しいです。はんだ使う時ディスプレイの損傷の可能性あるので、要注意。<br>
![](https://github.com/FuhaoSun/jetbot/raw/master/photos/2.jpg)<br>
##### 5.Wi-Fiカードは任意ですが、今度は無線LANアダプタを使用しています。（型番BUFFALO　WLI-UC-GNM2S）
##### 6.注意点：JetBotのOSイメージは通常版が64GBを超えているため128GB以上のmicroSDカードが必要になります。（64GBのmicroSDカードでも収まる63GBの縮小版イメージもありますが、後述の教師データの収集等を考えると、大きなサイズのmicroSDカードを準備することをお勧めします）
##### 7.公式Wikiのサンプル画像に間違っている箇所があります。

<div align=center><img width="150" height="150" src="https://github.com/FuhaoSun/jetbot/raw/master/photos/3.jpg"/></div>
##### 上記の画像では、左右のモーターの赤と黒のワイヤーが実際に裏返されています。<br>
##### これは損傷の原因にはなりませんが、モーターは逆回転します。それらを正しい方向に反転させてください。<br>



