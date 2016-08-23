# FastbootでのLinuxイメージのインストール(方法2)

DragonBoardへのイメージのインストールは、SDカードからのインストールと、Fastboot(Android系)によるインストールの2系統が用意されています。
本項では、Fastbootでのイメージのインストールに関して解説します。Fastbootは、Android開発ツールに含まれます。

* [SDからのイメージのインストール(方法1)](getting_started_sd.md)

## 準備するもの

* DragonBoad本体
* SDカード
* Android SDK([https://developer.android.com/studio/index.html?hl=ja](Android Studio)をインストールすれば含まれます)

## インストールするもの

DebianもしくはAndroidのイメージをインストール可能です。

* [http://builds.96boards.org/releases/dragonboard410c/linaro/debian/latest/dragonboard410c_sdcard_install_debian*.zip](Debian SD Card Install image)
* [http://builds.96boards.org/releases/dragonboard410c/qualcomm/android/latest/dragonboard410c_sdcard_install_android*.zip](Android SD Card Install image)

上記のいずれかのイメージをダウンロードしておきます。

## Fastbootでのイメージ焼き込み

S4のスイッチを押した状態で、電源をONにします。

![](/img/dev/dev004.png)

```bash
$ fastboot devices
```
http://builds.96boards.org/releases/dragonboard410c/linaro/rescue/latest/dragonboard410c_bootloader_emmc_linux*.zip

から、 eMMC用のパーティション生成ツールを取得します。

![](/img/dev/dev005.png)

```bash
$ cd dragonboard410c_bootloader_emmc_linux-46
$ ./flashall
```

eMMC内のデータの削除ができたので、今度は焼き込むイメージを用意します。

Debian Boot image
http://builds.96boards.org/releases/dragonboard410c/linaro/debian/latest/boot-linaro-jessie-qcom-snapdragon-arm64*.img.gz

Debian Root file system
http://builds.96boards.org/releases/dragonboard410c/linaro/debian/latest/linaro-jessie-developer-qcom-snapdragon-arm64*.img.gz

```bash
$ ls
linaro-jessie-developer-qcom-snapdragon-arm64-20151204-36.img.gz
boot-linaro-jessie-qcom-snapdragon-arm64-20151204-36.img.gz
$ gunzip *.gz
$ fastboot flash boot boot-linaro-jessie-qcom-snapdragon-arm64-20151204-36.img
$ flash rootfs linaro-jessie-developer-qcom-snapdragon-arm64-20151204-36.img
```
