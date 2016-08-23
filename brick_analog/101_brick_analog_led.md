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

OUT1コネクタにLED Brickを接続し、一定時間ごとに点灯/消灯させています。

```basic
100 'led_sample_program
110 OUT 1,1
120 WAIT 60
130 OUT 1,0
140 WAIT 60
150 GOTO 110
```

## 構成Parts
- 5mm LED(各色)

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/101_led
