# Xrdp  [Draft]
xrdpはIPアドレスを使用して，RDP接続を行うためのソフトウェア<br>
ローカルなネットワークでGUIによる遠隔操作を行うのに最適である<br>

## 注意書き
GUIでログインされているユーザについては，リモートからアクセスすることはできない(真っ黒な画面出力になる)<br>
システムをCUIでのログインに限定して運用するか，GUIでは必ずログアウトさせた状態にする必要がある<br>
上記の通り，**Chrome Remote Desktopなどとは相性が悪いため，現状はインストールをお勧めしない**<br>

## ダウンロード＆インストール
```bash
sudo apt update
sudo apt install xrdp
```

## 起動＆自動起動 設定
```bash
# xrdpの起動
sudo systemctl start xrdp

# xrdpの自動起動設定
sudo systemctl enable xrdp
```

## 初期設定
端末にGUIでログインしていると，その間GUIでの遠隔(同一ユーザでの)ログインができないため，ディスプレイ出力をCUIモードに切り替える
```
sudo systemctl set-default multi-user.target
```
