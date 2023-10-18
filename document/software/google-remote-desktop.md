# Google Remote Desktop
[Google Chrome](document/software/google-chrome.md)がインストール済みであることを前提とする<br>

## インストール
1. Chromeの「新しいタブ」の検索欄の下にあるChromeウェブストアにアクセス<br>

2. ストアの「ストアを検索」に「remote desktop」を入力し，検索<br>

3. Chrome Remote Desktopを選択し，「Chromeに追加」をクリック<br>

4. クリック後，アラートがされるが，その画面で「拡張機能を追加」をクリック<br>

5. Chromeの拡張機能一覧からGoogle Remote Desktopに入り，「リモートアクセス」タブを選択<br>

6. 一番下のこのデバイスから「同意してインストール」をクリックし，アプリをダウンロード<br>

7. ファイル(エクスプローラ)を開き，「ダウンロード」フォルダに移動<br>

8. マウスを右クリックし，「端末で開く」をクリックするとターミナルが開く<br>

```bash
# <ファイル名>には，実際にダウンロードしたファイルの名前を記述
sudo apt install ./<ダウンロードしたファイル名>.deb
```
を実行すると，インストールされる

※以下の初期設定まで終わらせていないと，利用することができない

# 初期設定
ターミナルを開き，<br>
```
sudo nano /opt/google/chrome-remote-desktop/chrome-remote-desktop
```

以下のような変更を加える<br>
```
# 2023/10/18時点での設定ファイルの編集

# launch_session関数の以下の部分をコメントアウト(先頭に#を付加)
# self._launch_server(server_args)
# if not self._launch_desktop_pre_session():
  # self.launch_desktop_session()

# 上記コメントアウト後，その直下に以下の内容を追加
display = self.get_unused_display_number()
self.child_env["DISPLAY"] = ":%d" % display

# get_unused_display_number関数の以下の部分をコメントアウト(先頭に#を付加)
# while os.path.exists(X_LOCK_FILE_TMPLATE % display):
  # display += 1
```

ターミナルで，
```
 mkdir ~/.config/chrome-remote-desktop
```
を実行する


再起動することで，ディスプレイ接続の有無に関わらず，リモートデスクトップが可能となる

※端末にディスプレイがつながっていないと，真っ黒な画面が出力されるため，ディスプレイ(仮想でも可)の接続が必要
