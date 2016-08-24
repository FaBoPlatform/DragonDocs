# FastbootでのLinuxイメージのインストール(方法2)

DragonBoardへのイメージのインストールは、SDカードからのインストールと、Fastboot(Android系)によるインストールの2系統が用意されています。
本項では、Fastbootでのイメージのインストールに関して解説します。Fastbootは、Android開発ツールに含まれます。

* [SDからのAndroidイメージのインストール](dev/getting_started_sd_android.md)

## 準備するもの

* DragonBoad本体
* SDカード
* Android SDK([https://developer.android.com/studio/index.html?hl=ja](Android Studio)をインストールすれば含まれます)

## Fastbootでのイメージ焼き込み

S4のスイッチを押した状態で、電源をONにします。

![](/img/dev/dev004.png)

```bash
$ fastboot devices
```
http://builds.96boards.org/releases/dragonboard410c/linaro/rescue/latest/dragonboard410c_bootloader_emmc_android*.zip

から、 AndroidのBootloaderとのeMMCパーティション生成ツールを取得します。

![](/img/dev/dev005.png)

```bash
$ cd 解凍先のフォルダ
$ ./flashall
```
eMMC内のデータの削除されBootloaderが書き込まれます。

今度は焼き込むイメージを用意します。
今回は、16.03のRepositoryにある各種Imageを使用します。

http://builds.96boards.org/releases/dragonboard410c/qualcomm/android/16.03/


```bash

