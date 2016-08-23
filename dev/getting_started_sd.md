# SDからのイメージのインストール(方法1)

DragonBoardへのイメージのインストールは、SDカードからのインストールと、Fastboot(Android系)によるインストールの2系統が用意されています。
本項では、SDからのイメージのインストールに関して解説します。Fastbootからのインストールの方法を知りたい方は、下記を参照ください。

* [FastbootからのLinuxイメージのインストール(方法2)](getting_started_fastboot_linux.md)
* [FastbootからのAndroidイメージのインストール(方法2)](getting_started_fastboot_android.md)


## 準備するもの

* DragonBoad本体
* SDカード

## インストールするもの

DebianもしくはAndroidのイメージをインストール可能です。

* [Debian SD Card Install image](http://builds.96boards.org/releases/dragonboard410c/linaro/debian/latest/dragonboard410c_sdcard_install_debian*.zip]
* [Android SD Card Install image](http://builds.96boards.org/releases/dragonboard410c/qualcomm/android/latest/dragonboard410c_sdcard_install_android*.zip]

上記のいずれかのイメージをダウンロードしておきます。

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

## インストールしたいイメージをDDコマンドでSDカードに焼き込む

DragonBoardのイメージをダウンロードし解凍し、*.img形式のデータを、ddコマンドでSDカードに焼き込みます。

* [Debian SD Card Install image](http://builds.96boards.org/releases/dragonboard410c/linaro/debian/latest/dragonboard410c_sdcard_install_debian*.zip)
* [Android SD Card Install image](http://builds.96boards.org/releases/dragonboard410c/qualcomm/android/latest/dragonboard410c_sdcard_install_android*.zip)


Debianイメージの場合
```bash
$ cd 解凍先のフォルダ
$ ls 
$ sudo dd if=db410c_sd_install_android.img of=/dev/rdisk4
```

Androidイメージの場合
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

