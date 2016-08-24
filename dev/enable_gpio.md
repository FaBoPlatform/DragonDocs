# DebianでGPIOを有効にする

Debian上でGPIOを有効にする方法の解説です。

## Networkに接続する

DragonBoardをネットワークに接続します。　

## パッケージのUpdate

```bash
$ sudo apt-get update
```

## GPIOライブラリをコンパイルするためのtoolを追加

```bash
$ sudo apt-get install autoconf automake libtool
```

## Libsoc

```bash
$ git clone https://github.com/jackmitch/libsoc.git
$ cd libsoc
$ autoreconf -i
$ ./configure --enable-board="dragonboard410c"
$ make
$ sudo make install
```

## 96BoardsGPIO

96BoardsGPIO GitHubリポジトリからクローンしてコンパイルします。

```bash
$ git clone 
$ cd 96BoardsGPIO
$ ./autogen.sh
$ ./configure
$ make
$ sudo make install
$ sudo ldconfig
```

## TEST

GPIO-AにLED Brickを接続します。

```bash
$ cd 96BoardsGPIO/examples
$ make
$ sudo ./blink
```

```bash
#!/usr/bin/python
import time

from gpio_96boards import GPIO

GPIO_A = GPIO.gpio_id('GPIO_A')
pins = (
    (GPIO_A, 'out'),
)


def blink(gpio):
    for i in range(5):
        gpio.digital_write(GPIO_A, GPIO.HIGH)
        time.sleep(i)
        gpio.digital_write(GPIO_A, GPIO.LOW)
        time.sleep(1)


if __name__ == '__main__':
    import argparse

    parser = argparse.ArgumentParser(
        description='Blink LED on GPIO A (pin 23)')
    args = parser.parse_args()

    with GPIO(pins) as gpio:
        blink(gpio)
```