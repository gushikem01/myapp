## WSLでflutterをインストールする方法

wsl2でflutterのリポジトリをgitcloneする時、dnsエラーになるため、以下を実行する。

sudo sh -c "echo 'nameserver 8.8.8.8' > /etc/resolv.conf"

cd /home/gushikem/work/flutter_sample
sudo git clone https://github.com/flutter/flutter.git -b stable

sudo vi ~/.bashrc
export PATH=$PATH:/home/gushikem/work/flutter_sample/flutter/bin
source ~/.bashrc
which flutter

## パーミッション変更

chown -R gushikem:gushikem flutter

## Flutter Config

flutter config --enable-web
flutter doctor

## Portable Apps Chromeインストール

ダウンロード
GoogleChromePortable_96.0.4664.110_online.paf.exe

sudo vi ~/.bashrc
export CHROME_EXECUTABLE=/mnt/c/app/GoogleChromePortable/GoogleChromePortable.exe
source ~/.bashrc

## プロジェクトを作成

flutter create myapp
cd ./myapp

## ビルドイン Webサーバーを起動

flutter run -d web-server

すると、ブラウザが起動してFlutterのサンプルが表示されます。

