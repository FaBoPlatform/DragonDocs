# #101 LED Brick

<center>![](/img/100_analog/product/101.jpg)
<!--COLORME-->

## Overview
LEDのBrickです。発光色は5色（青・緑・赤・白・黄）あります。Lチカのおともにもどうぞ。

※購入時は色の間違いにご注意ください。

## Connecting

OUTコネクタのいずれかに接続します。

## Schematic
![](/img/100_analog/schematic/101_led.png)

## Sample Code

GPIO-AコネクタにLED Brickを接続し、一定時間ごとに点灯/消灯させています。

```Python
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

## 構成Parts
- 5mm LED(各色)

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/101_led
