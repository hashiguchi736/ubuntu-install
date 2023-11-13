# Wine
以下の公式サイト通り行うことで，インストールまで完了する<br>

## インストール手順
32bitパッケージインストールの追加(64bit版OSを使用している場合)
```
sudo dpkg --add-architecture i386 
```

### Wineリポジトリをパッケージリストに追加
```
sudo mkdir -pm755 /etc/apt/keyrings
sudo wget -O /etc/apt/keyrings/winehq-archive.key https://dl.winehq.org/wine-builds/winehq.key
```

```
# Ubuntu22.04を使用している場合
sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/ubuntu/dists/jammy/winehq-jammy.sources
```

### パッケージリストの更新
```
sudo apt update
```
```
sudo apt install --install-recommends winehq-stable
```
ここまでの手順が完了すると、インストールが完了する<br>

## 文字化け対策
ターミナルを開き, 
```
sudo apt install winetricks
winetricks
```
GUIウィンドウが開いたら, 
「Select the default wineprefix」→「Install a font」→「cjkfonts」でフォントをインストールする<br>
インストール中, 幾度となく警告ダイアログが表示されるが, 無視して進む<br>

## Windowsアプリの実行
ダウンロードなどしてきた.exeファイルを「ファイルマネージャー」上で右クリックし, 「別のアプリケーションで開く」を選択<br>
「Wine Windows プログラムローダー」を選択すると, Wine越しに実行することができる<br>

Linux上で完全にWindowsアプリが動くわけではないことに注意<br>

## 参考URL
[Wine公式HP](https://wiki.winehq.org/Ubuntu)
