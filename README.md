# Raspberry Piのセットアップについて  
## SDからデータをコピーする  
初期設定のバックアップデータは各々USBに残しておく。  
サーバーにも上げておく。  
バックアップデータをSDカードに複製する。  
[SD Card CopyerでラズパイのSDカードを複製](https://qiita.com/ikemura23/items/4b7ab1af98045fa6516b)

全部ひとりで設定したい人は以下の項目を行う。

  - Raspberry PiのOSインストール、初期設定  
  [RaspberryPiの初期セッティング](https://qiita.com/S_ODA/items/3600b4492747e66f5df7)
  - Gitインストール  
  [ラズパイ3 gitインストール](https://qiita.com/natacom/items/63cca20e24e3e864e485)  
  「Gitに自分が誰か教える」まででいい。
  - OpenCVのインストール  
  [OpenCV + Python3 on Raspberry Pi](https://qiita.com/nanbuwks/items/422eb405ceef84826ab4)
  - pigpioのインストール  
  [Raspberry PiのGPIO制御の決定版pigpioを試す](https://karaage.hatenadiary.jp/entry/2017/02/10/073000)  
  インストールだけすればいい
  - ディレクトリの整理  
  以下のようにディレクトリを整理する。 　
  <pre>
  home  
    ├ pi  
    ├ git  
    |   ├ kimuralab  
    |       このディレクトリの中はGitHubと同じ構成にする
    | 
    ├ Opencv  //このディレクトリはOpenCVライブラリ用
  </pre>    

## GitHubディレクトリの整理

まずGitHubアカウントを自分のものに変更する。  
`git config --global user.name "自分のユーザーネーム" `  
`git config --global user.email 自分のメールアドレス`  

gitフォルダの中のkimuralabフォルダの中をGitHubと同じディレクトリ構成にする
例えばSensorModuleTestディレクトリを作りたい場合は

`mkdir SensorModuleTest`  
`cd SensorModuleTest`  
`mkdir GPS`  
`cd GPS`  
`git init`  
`git clone https://github.com/cansat2019kimuralab/SensorModuleTest/GPS master`  

ほかのフォルダをクローンしたい場合も同様。

とりあえず、セットアップは以上で終わり。

BBMもEndToEndもすべてのプログラムはkimuralabフォルダに保存し、gitにアップすること。  
各モジュールの試験はMasterに挙げる。  
EndToEnd試験や大会用プログラムはbranchに挙げること（詳細はオイオイ）。
