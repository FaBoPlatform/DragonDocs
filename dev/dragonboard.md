# DragonBoardについて

スマートフォン向けに提供されているQualcomm製 4コア搭載アプリケーションプロセッサーをベースとしたプロトタイピングボード。

## CPU

| NAME | スペック | 
|:--|:--|
| Qualcomm Snapdragon 410 | Quad-core ARM® Cortex® A53(1.2 GHz) |
| Qualcomm Adreno 306 | 400MHz GPU |

## Support OS

| OS |  Android 5.1<br>Ubuntu<br>Windows 10 IoT | 
|:--|:--|


## PIN Assign

| PIN | 96Boards Signals | 410c Signals |
|:--|:--|:--|
| 1 | GND | GDN |
| 3 | UART0_CTS | UART0_CTS_N (APQ GPIO_2) |
| 5 | UART0_TxD | UART0_TX (APQ GPIO_0) |
| 7 | UART0_RxD | UART0_RX (APQ GPIO_1) |
| 9 | UART0_RTS | UART0_CTSN_B(APQ GPIO_3) |
| 11 | UART1_TxD | UART1_TX (APQ GPIO_4) |
| 13 | UART1_RxD | UART1_RX (APQ GPIO_5) |
| 15 | I2C0_SCL | I2C0_SCL (APQ GPIO_7) |
| 17 | I2C0_SDA | I2C0_SDA (APQ GPIO_6) |
| 19 | I2C1_SCL | I2C1_SCL (APQ GPIO_23) |
| 21 | I2C1_SDA | I2C1_SDA (APQ GPIO_22) |
| 23 | GPIO-A | LS_EXP_GPIO_A (APQ GPIO_36) (APQ INT) |
| 25 | GPIO-C | LS_EXP_GPIO_C (APQ GPIO_13) (TS_INT_N) |
| 27 | GPIO-E | LS_EXP_GPIO_E (APQ GPIO_115) (GYRO_ACCL_INT_N) |
| 29 | GPIO-G | LS_EXP_GPIO_G (APQ GPIO_24) (DSI_VSYNC) |
| 31 | GPIO-I | LS_EXP_GPIO_I (APQ GPIO_35) (CSI0_RST) |
| 33 | GPIO-K | LS_EXP_GPIO_K (APQ GPIO_28) (CSI1_RST) |
| 35 | +1V8 | LS_EXP_1P8 |
| 37 | +5V | SYS_5P0 |
| 39 | GND | GND |

| PIN | 96Boards Signals | 410c Signals |
|:--|:--|:--|
| 2 | GND | GND |
| 4 | PWR_BTN_N | PHONE_ON_N |
| 6 | RST_BTN_N | PM_RESIN_N |
| 8 | SPI0_SCLK | SPI0_CLK (APQ GPIO_19) |
| 10 | SPI0_DIN | SPI0_MISO (APQ GPIO_17) |
| 12 | SPI0_CS | SPI0_CS_N (APQ GPIO_18) |
| 14 | SPI0_DOUT | SPI0_MOSI (APQ GPIO_16) |
| 16 | PCM_FS | LS_EXP_MI2S_WS (APQ GPIO_110) |
| 18 | PCM_CLK | LS_EXP_MI2S_SCK (APQ GPIO_113) (ALPS_INT) |
| 20 | PCM_DO | LS_EXP_MI2S_DATA0 (APQ GPIO_114) |
| 22 | PCM_DI | N.C. I2S |
| 24 | GPIO-B | LS_EXP_GPIO_B (APQ GPIO_12) (TS_RST_N) |
| 26 | GPIO-D | LS_EXP_GPIO_D (APQ GPIO_69) (MAG_INT) |
| 28 | GPIO-F | LS_EXP_GPIO_F (PM_MPP_4) (DSI_BLCTRL)) |
| 30 | GPIO-H | LS_EXP_GPIO_H (APQ GPIO_25) (DSI_RST) |
| 32 | GPIO-J | LS_EXP_GPIO_J (APQ GPIO_34) (CSI0_PWDN) |
| 34 | GPIO-L | LS_EXP_GPIO_L (APQ GPIO_33) (CSI1_PWDN) |
| 36 | SYS_DCIN | SYS_DCIN |
| 38 | SYC_DCIN | SYS_DCIN |
| 40 | GND | GND |