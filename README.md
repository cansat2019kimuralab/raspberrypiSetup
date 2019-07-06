# Raspberry Piのセットアップについて  
## SDからデータをコピーする  
初期設定のバックアップデータは各々USBに残しておく。  
サーバーにも上げておく。  
バックアップデータをSDカードに複製する。  
[SD Card CopyerでラズパイのSDカードを複製](https://qiita.com/ikemura23/items/4b7ab1af98045fa6516b)

全部ひとりで設定したい人は以下の項目を行う。
  - Raspberry PiのOSインストール、初期設定  
  [RaspberryPiの初期セッティング](https://qiita.com/S_ODA/items/3600b4492747e66f5df7)
  - pip3のインストール  
  [Ubuntuでpip / pip3がインストールできないときの対処法 | Python2 / 3](https://www.bioerrorlog.work/entry/install-pip-pip3-ubuntu#apt-update%E3%81%97%E3%81%A6%E3%81%8B%E3%82%89apt-install%E3%81%99%E3%82%8B--pip--pip3)  
  「apt updateしてからapt installする : pip○ / pip3○」だけやればよい
  - OpenCVのインストール   
  [Raspberry Pi で OpenCV 4](https://qiita.com/tomo_vn/items/eea677eb00488d4c2291)  
  OpenCV3の場合はこっち　[OpenCV + Python3 on Raspberry Pi](https://qiita.com/nanbuwks/items/422eb405ceef84826ab4) 
  これでもうまくいった　[OpenCVのインストール](https://homemadegarbage.com/raspizero-opencv)  
  OpenCVのインストールは非常に気まぐれ、上手くいくまで色々試す  
  - pigpioのインストール  
  [Raspberry PiのGPIO制御の決定版pigpioを試す](https://karaage.hatenadiary.jp/entry/2017/02/10/073000)  
  インストールとデーモンの自動立ち上げだけ設定すればいい  
  `sudo apt-get update`  
  `sudo apt-get install pigpio`  
  `sudo nano /etc/rc.local`  
  rc.localの最後に`sudo pigpiod`を記入する  
  - I2Cの設定  
  [Python3 から I2C を使いたい](http://nucl.hatenablog.com/entry/2017/09/29/151411)  
  - 無線モジュールの設定  
  [Raspberry PiでGPIOを使用したシリアル通信](https://www.ingenious.jp/raspberry-pi/2019/03/gpio-uart/)  
  [Raspberry PiでIM920のシリアル通信を受信](https://blog.goo.ne.jp/izumame/e/4bf0f69ec24947bdde42a66b365e43d7)  
  [Raspberry Pi3Bのシリアルコンソール・シリアル通信について](http://yueno.net/xoops/modules/xpwiki/?PC%2FRaspberryPi%2FPi3%E3%81%AE%E3%82%B7%E3%83%AA%E3%82%A2%E3%83%AB%E9%80%9A%E4%BF%A1)  
  - ディレクトリの整理  
  以下のようにディレクトリを整理する。 　
  <pre>
  home  
    ├ pi  
    ├ git  
    |   ├ kimuralab  
    |       このディレクトリの中はGitHubと同じ構成にする
    | 
    ├ opencv  //このディレクトリはOpenCVライブラリ用 
    ├ opencv_contrib  //このディレクトリはOpenCVライブラリ用
  </pre>    

## GitHubディレクトリの整理
まずGitHubアカウントを自分のものに変更する。  
`git config --global user.name "自分のユーザーネーム" `  
`git config --global user.email 自分のメールアドレス`  

gitフォルダの中のkimuralabフォルダの中をGitHubと同じディレクトリ構成にする  
例えばSensorModuleTestを入れたい場合は

`git clone https://github.com/cansat2019kimuralab/SensorModuleTest`  

ほかのフォルダをクローンしたい場合も同様。

# IPアドレスの固定
SSH接続する場合はIPアドレスを固定する必要がある。  
[Raspberry Pi に固定IPアドレスを割り当てる方法（Raspbian Jessie）](https://qiita.com/marie_khr/items/b088ffb252a92eee8f5d)  
割り当て可能なIPアドレスはローカルウィキの「ネットワーク関係」を参照  
interface0はコメントアウトしたまま  
static ip_addressに設定したい固定IPアドレス  
static routersにはゲートウェイのアドレス  
static domain_name_serversはコメントアウトしたまま

# とりあえず、セットアップは終わり
BBMもEndToEndもすべてのプログラムはkimuralabフォルダに保存し、gitにアップすること。  
各モジュールの試験はMasterに挙げる。  
EndToEnd試験や大会用プログラムはbranchに挙げること（詳細はオイオイ）。

# トラブルシューティング
- [leafpad 設定](https://achapi2718.blogspot.com/2013/10/leafpad.html)
- [【Raspberry Pi】apt-get updateで失敗する](http://engetu21.hatenablog.com/entry/2015/04/11/131949)
