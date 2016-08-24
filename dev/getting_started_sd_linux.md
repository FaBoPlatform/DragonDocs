# SDからのイメージのインストール(方法1)

DragonBoardへのイメージのインストールは、SDカードからのインストールと、Fastboot(Android系)によるインストールの2系統が用意されています。
本項では、SDからのイメージのインストールに関して解説します。Fastbootからのインストールの方法を知りたい方は、下記を参照ください。

* [FastbootからのLinuxイメージのインストール](getting_started_fastboot_linux.md)

## 準備するもの

* DragonBoad本体
* SDカード

## イメージのRepository

* [Debian Repository(http://builds.96boards.org/releases/dragonboard410c/linaro/debian/)

## SDカードのディレクトリを取得

MacBookにSDカードを挿し、SDカードのディレクトリを確認します。(以下、SDカードが/dev/disk4だった場合の解説)

```bash
$ sudo diskutil list
```

## SDカードをアンマウント

SDカードをアンマウントします。

```bash
$ sudo diskutil unmountDisk /dev/disk4
```

## DebianのイメージをDDコマンドでSDカードに焼き込む

* [Debian](http://builds.96boards.org/releases/dragonboard410c/linaro/debian/)
[Image version 100](http://builds.96boards.org/releases/dragonboard410c/linaro/debian/16.06/dragonboard410c_sdcard_install_debian-110.zip)で動作

今回は、[Image version 100](http://builds.96boards.org/releases/dragonboard410c/linaro/debian/16.06/dragonboard410c_sdcard_install_debian-110.zip)をダウンロードします。

Debianイメージの場合

```bash
$ cd 解凍先のフォルダ
$ ls 
$ sudo dd if=db410c_sd_install_android.img of=/dev/rdisk4
```

## DragonBoardでの実行

DragonBoard410にSDカードを差し込み、DIP Switchの2番をONにして再起動します。

![](/img/dev/dev001.png)

DIP Switchの意味

|スイッチ | 意味 |
|:--|:--|
|Switch 1 | onでUSB BOOT |
|Switch 2 | onでSD BOOT(今回はここをON) | 
|Switch 3 | USB HOSTの設定 |
|Switch 4 | HDMI SELの設定 |

Installメニューがあらわれるので、Imageを選択しInstall(i)を選択し、ImageをeMMC(Flashメモリ)にコピーします。

![](/img/dev/dev006.png)

DIP Switchを元どおりにして、再起動します。

![](/img/dev/dev003.png)


