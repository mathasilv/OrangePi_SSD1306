# **OrangePiZero3 - SSD1306**

Add an OLED display to your OrangePiZero3 with system info!

## **Setup**

First, you need to have [WiringPi] installed and enable the I2C module.

If you are using the official Debian image of the OrangePiZero3, just run `sudo orangepi-config`, go to System > Hardware, select `ph-i2c3`, and then Save.

After that, clone the repository:
```sh
https://github.com/mathasilv/OrangePi_SSD1306.git
```

Then, build the executable file with:

```sh
cd ./OrangePi_SSD1306
make clean all 
chmod +x ./display.out
```

Now, you need to connect the screen to your OrangePi Zero 3 following the table below:

| SSD1306 | OrangePi | 
|:-------:|:--------:|
| VCC     | 3.3v     |
| GND     | GND      |
| SDA     | SDA      |
| SCL     | SCL      |

![Orange Pi SSD1306](https://github.com/mathasilv/OrangePi_SSD1306/raw/main/pictures/0627-zero3%20(11).png)

The program **also requires a button to wake up the screen**. The button should be connected to the **WPi 13** pin and the **0v** pin.

After this, run the program:
```sh
sudo ./display.out
```

You can add a cron job to run the program each time the system boots up with the command `sudo crontab -e` and add the following line at the end:
```
@reboot /<path to the folder>/display.out
```

[WiringPi]: <https://github.com/orangepi-xunlong/wiringOP>
[armbian]: <https://www.armbian.com/>

---

Essa versão corrige pequenos erros de digitação e melhora a clareza e a fluidez do texto.
