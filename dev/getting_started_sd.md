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

* [http://builds.96boards.org/releases/dragonboard410c/linaro/debian/latest/dragonboard410c_sdcard_install_debian*.zip](Debian SD Card Install image)
* [http://builds.96boards.org/releases/dragonboard410c/qualcomm/android/latest/dragonboard410c_sdcard_install_android*.zip](Android SD Card Install image)

上記のいずれかのイメージをダウンロードしておきます。

## イメージの作成(OS X, El capitan)

MacBookにSDカードを挿し、SDカードのディレクトリを確認します。(以下、SDカードが/dev/disk4だった場合の解説)

```bash
$ sudo diskutil list
```

SDカードをマウントします。。


```bash
$ sudo diskutil unmountDisk /dev/disk4
```

DragonBoardのイメージをSDカードに焼き込みます。

Debianイメージの場合
```bash
$ sudo dd if=db410c_sd_install_android.img of=/dev/rdisk4
```

Androidイメージの場合
```bash
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

