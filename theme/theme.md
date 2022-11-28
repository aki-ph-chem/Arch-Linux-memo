# xfce4でテーマをカスタムする

デフォルトでも好きだけど、ちょっと手を加えるとよりかっこよく・可愛くカスタムすることができる。

## テーマの設定

1. お好みのテーマをダウンロードする。
2. ファイル(.zip, .tar.xz .. etc)を解凍して/usr/share/themesに配置する
3. settings -> Appearance と　Setting -> Window Managerでテーマを変更する

## アイコンの設定

テーマに加えてアイコンもカスタムするとよりカスタムできる。

1. お好みのアイコンをダウンロードする。
2. ファイル(.zip, .tar.xz .. etc)を解凍して/usr/share/iconsに配置する
3. settings -> Appearance -> icons でアイコンテーマを変更する

## フォルダとディレクトリ

ファイルマネージャにてDesktop,Musicなどの"一般的な"ディレクトリにアイコンが適用されない場合にはxdg-user-dirsを用いるとうまくいく。

- xdg-user-dirs: インストール
    - $ sudo pacman -S xdg-user-dirs

- $HOME下にローカライズされたディレクトリを作成する
    - $ xdg-user-dirs-update 

- 設定ファイル
    - デフォルトの設定ファイルは ~/.config/user-dirs.dirsと/etc/xdg/user-dirs.defaultsにある
