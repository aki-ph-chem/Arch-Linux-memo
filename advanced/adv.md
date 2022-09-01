# デスクトップ環境(Xfce4)を構築後の種々の設定

デスクトップ環境を構築した後で必要になった種々の設定のメモ。

## サウンド

サウンドクライアントとしては　pulseaudioをインストールする

> $ sudo pacman -S pulseaudio

このままでは、GUIでの調整ができないためGUIのクライアントもインストールする。

> $ sudo pacman -S pavucontorol

## wifi接続

参考: 1) https://aznote.jakou.com/archlinux/wireless.html
      2) https://wiki.archlinux.jp/index.php/Netctl 


毎回wpa_supplicantで手動でwifi接続をするのは骨が折れるのでnetctlを導入する。

### netctl 

インストール

> $ sudo pacman -S netctl

なお、依存パッケージとしてはdhcpcd, wpa_supplicantが必要である。

### 設定

/etc/netctl/examples にあるサンプルから必要なものを選び /etc/netctl/に適当な名前
をつけてコピーする。たいていの場合wireless-wpaでok。

次にそのファイルを開きInterface, ESSID, Key に書き込む。

次にインターフェイスをdownする

> sudo iplink set [interface-name] down

最後に

> sudo netctl start [profile_name]
 
として接続する。

切断する際には

> sudo netctl stop [profile_name]

とする。

### 自動接続

> netctl enable [profile_name]

とすれば起動時にデーモンが起動する。


## ブートローダー

参考

> https://forum.manjaro.org/t/warning-os-prober-will-not-be-executed-to-detect-other-bootable-partitions/57849/2

> https://h3poteto.hatenablog.com/entry/2021/03/20/234446

> https://wiki.archlinux.jp/index.php/GRUB#.E3.83.87.E3.83.A5.E3.82.A2.E3.83.AB.E3.83.96.E3.83.BC.E3.83.88

### os-proberでデュアルブート

> sudo pacman -S os-prober

でos-proberをインストール。

現在のバージョンではos-proberが動作しないように設定されているため、/etc/default/grubに

> GRUB_DISABLE_OS_PROBER=false

と追加して

> sudo update-grub

とする
