# SDからのイメージのインストール(方法1)

DragonBoardへのイメージのインストールは、SDカードからのインストールと、Fastboot(Android系)によるインストールの2系統が用意されています。
本項では、SDからのイメージのインストールに関して解説します。Fastbootからのインストールの方法を知りたい方は、下記を参照ください。

* [FastbootからのLinuxイメージのインストール(方法2)](getting_started_fastboot_linux.md)
* [FastbootからのAndroidイメージのインストール(方法2)](getting_started_fastboot_android.md)


## 準備するもの

* DragonBoad本体
* SDカード

## イメージのRepository

* [Debian Repository(http://builds.96boards.org/releases/dragonboard410c/linaro/debian/]
* [Android Repositiry](http://builds.96boards.org/releases/dragonboard410c/qualcomm/android/]

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

## AndroidのイメージをDDコマンドでSDカードに焼き込む

DragonBoardのイメージをダウンロードし解凍し、*.img形式のデータを、ddコマンドでSDカードに焼き込みます。

* [Android](http://builds.96boards.org/releases/dragonboard410c/qualcomm/android/)
[ImageVersion #99](http://builds.96boards.org/releases/dragonboard410c/qualcomm/android/16.03/dragonboard410c_sdcard_install_android-99.zip)は正常動作、[ImageVersion #118](http://builds.96boards.org/releases/dragonboard410c/qualcomm/android/16.06/dragonboard410c_sdcard_install_android-118.zip)が「Unfortunately, the process com.android.phone has stopped」のエラーがでてまともに操作できず。

今回は、[ImageVersion #99](http://builds.96boards.org/releases/dragonboard410c/qualcomm/android/16.03/dragonboard410c_sdcard_install_android-99.zip)のイメージをダウンロードします。

```bash
$ cd 解凍先のフォルダ
$ ls
$ db410c_sd_install_android.img	license.txt
$ sudo dd if=db410c_sd_install_android.img of=/dev/rdisk4 bs=4m 
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

![](/img/dev/dev002.png)

DIP Switchを元どおりにして、再起動します。

![](/img/dev/dev003.png)

Androidの場合、初回再起動時には、起動に2分程度時間があかります。

