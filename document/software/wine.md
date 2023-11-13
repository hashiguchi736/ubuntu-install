# Wine
以下の公式サイト通り行うことで，インストールまで完了する<br>

# 手順
### インストール手順
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

## 参考URL
[Wine公式HP](https://wiki.winehq.org/Ubuntu)
