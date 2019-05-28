# Raspberry Piのセットアップについて

OSのインストールとpigpioのインストールは

## Raspberry PiのOSインストール、初期設定について

[RaspberryPiの初期セッティング](https://qiita.com/S_ODA/items/3600b4492747e66f5df7)

## Gitインストール
  
[ラズパイ3 gitインストール](https://qiita.com/natacom/items/63cca20e24e3e864e485)

## OpenCVのインストール

[OpenCV](https://qiita.com/nanbuwks/items/422eb405ceef84826ab4)

## pigpioのインストール

[Raspberry PiのGPIO制御の決定版pigpioを試す](https://karaage.hatenadiary.jp/entry/2017/02/10/073000)

## ディレクトリの整理

以下のようにディレクトリを整理する。　　
<pre>
 home  
 　├ pi  
  　 ├ git  
  　 |   ├ kimuralab  
  　 |       このディレクトリの中はGitHubと同じ構成にする
   　| 
   　|- Opencv  //このディレクトリはOpenCVライブラリ用
</pre>    

## GitHubディレクトリの整理

gitフォルダの中のkimuralabフォルダの中をGitHubと同じディレクトリ構成にする
例えばSensorModuleTestディレクトリを作りたい場合は

'mkdir SensorModuleTest'
'cd SensorModuleTest'
'mkdir GPS'
'cd GPS'
'git init'
'git clone https://github.com/cansat2019kimuralab/SensorModuleTest/GPS master'

ほかのフォルダをクローンしたい場合も同様。
