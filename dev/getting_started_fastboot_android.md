# FastbootでのAndroidイメージのインストール(方法2)

DragonBoardへのイメージのインストールは、SDカードからのインストールと、Fastboot(Android系)によるインストールの2系統が用意されています。
本項では、Fastbootでのイメージのインストールに関して解説します。Fastbootは、Android開発ツールに含まれます。

* [SDからのイメージのインストール(方法1)](getting_started_sd.md)

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

から、 eMMC用のパーティション生成ツールを取得する。

```bash
$ cd dragonboard410c_bootloader_emmc_android-46
$ ./flashall
```

