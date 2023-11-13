# AnyDesk

## ダウンロード
[ダウンロードページ](https://anydesk.com/ja/downloads/linux)からOS・CPUアーキテクチャ・バージョンを指定して，ダウンロード<br>
Raspberry Piを使用している場合は，[ダウンロードページ](https://anydesk.com/ja/downloads/raspberry-pi)

## インストール
1. ファイル(エクスプローラ)を開き，「ダウンロード」フォルダに移動<br>

2. マウスを右クリックし，「端末で開く」をクリックするとターミナルが開く<br>

   ```bash
   # <ファイル名>には，実際にダウンロードしたファイルの名前を記述
   sudo apt install ./<ダウンロードしたファイル名>.deb
   ```
   を実行すると，インストールされる<br><br>

   === **Rapsberry Piを使用している場合は，以下の手順も必要になる** ===<br>
   ```
   # armhfパッケージもインデックス取得の対象に追加
   sudo dpkg --add-architecture armhf

   # パッケージリストの更新
   sudo apt update

   # パッケージのインストール
   sudo apt install libpolkit-gobject-1-0:armhf libraspberrypi0:armhf libraspberrypi-dev:armhf libraspberrypi-bin:armhf libgles-dev:armhf libegl-dev:armhf

   # 自動パーミッションの割り当て
   echo 'SUBSYSTEM=="vchiq",GROUP="video",MODE="0666"' | sudo tee /etc/udev/rules.d/10-vchiq-permissions.rules
   ```

## 自動起動設定
以下のコマンドで，自動起動の設定を行う<br>

```
sudo systemctl enable anydesk
```

## 状態確認
以下のコマンドで，簡易的なログや起動しているかどうかの状態を確認することができる<br>
```
sudo systemctl status anydesk
```
