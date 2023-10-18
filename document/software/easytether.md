# Easytether

## ダウンロード
[ダウンロードページ](http://www.mobile-stream.com/easytether/drivers.html)からUbuntu20.04のamd64版をダウンロード<br>
※執筆時には最新版がUbuntu20.04であるため，選択している(最新版が更新されていれば，変更すること)

## インストール
1. ファイル(エクスプローラ)を開き，「ダウンロード」フォルダに移動<br>

2. マウスを右クリックし，「端末で開く」をクリックするとターミナルが開く<br>

   ```bash
   # <ファイル名>には，実際にダウンロードしたファイルの名前を記述
   sudo apt install ./<ダウンロードしたファイル名>.deb
   ```
   を実行すると，インストールされる<br>
   

   ```bash
   依存：　libssl1.1 ...
   ```
   のようなエラーが出た場合には，以下の手順を行ってから再度インストールする必要がある<br>

   ```
   # ここではlibssl1.1_1.1.1f-1ubuntu2.19_amd64.debをダウンロードしているが，openssl1.1系の最新版をダウンロードする必要がある
   # libopensslとopensslといったパッケージが混在するが，ライブラリのみのインストールパッケージであるlibopensslをダウンロードすること

   wget http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2.19_amd64.deb
   sudo apt install ./<ダウンロードしたファイル名>.deb
