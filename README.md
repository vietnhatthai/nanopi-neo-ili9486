# ILI9486 Nanopi Neo Core/Core2

```
pi@nanopineo:~$ uname -a
Linux nanopineo 6.6.36-current-sunxi #1 SMP Thu Jun 27 11:49:15 UTC 2024 armv7l armv7l armv7l GNU/Linux
```

Wiring between ILI9486 and NanoPi Neo

```
3.3v   <-->  VCC & LED
GND    <-->  GND
PA14   <-->  SCK       & T_CLK <SPI1>
PA16   <-->  SDO<MISO> & T_DO  <SPI1>
PA15   <-->  SDI<MOSI> & T_DIN <SPI1>
PG9    <-->  DC
PA1    <-->  RESET
PA13   <-->  CS
PA17   <-->  T_CS
PA0    <-->  T_IRG
```

This is the /boot/armbianEnv.txt
```
overlays=spi1
user_overlays=fbtft-ili9486
```

Compile device tree
```
armbian-add-overlay /path/to/fbtft-ili9486.dts
```

Test

```
# apt install fbi
fbi -T 2 -d /dev/fb0 -a image.jpg
```

Demo

<img src="https://raw.githubusercontent.com/vietnhatthai/nanopi-neo-ili9486/main/demo.jpg" height="256"/>

Hardware

[NanoPi NEO Core](https://www.friendlyelec.com/index.php?route=product/product&product_id=212&search=Neo+core&description=true&category_id=0)

[Mini Shield for NanoPi NEO Core/Core2](https://www.friendlyelec.com/index.php?route=product/product&product_id=213&search=Neo+core&description=true&category_id=0)

[MHS-3.5inch RPi Display](http://www.lcdwiki.com/MHS-3.5inch_RPi_Display)

References

[Hackaday - Armbian, NanoPi and ILI9341 Touch](https://hackaday.io/project/190371-g-edm/log/217902-first-success-with-armbian-nanopi-and-ili9341-touch) 
