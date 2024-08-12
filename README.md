# **OrangePi - SSD1306**

Add a OLED display to your OrangePi with the system info!

## **Setup**

First you need to have the [WiringPi] installed and enable the I2C module.

If you use the oficial debian image of oragepizero3, just run `sudo orangepi-config` and go to System > Hardware select ph-i2c3 and then Save;


After that, clone the repository:
```sh
https:/github.com/mathasilv/OrangePi_SSD1306.git
```


Then build the executable file with:

```sh
cd ./OrangePi_SSD1306
make clean all 
chmod +x ./display.out
```

Now you need to connect the screen to your OrangePi following the next table:

| SSD1306 | OrangePi | 
|:-------:|:--------:|
| VCC | 3.3v |
| GND | GND  |
| SDA | SDA  |
| SDK | SCL  |

The program **needs also a button to wake up the screen**, this button should be connected between the `WPi 13` pin and the `0v` pin;

After this run the program:
```sh
sudo ./display.out
```

You can add a cron job to run the program each time the system boots up with the command `sudo crontab -e` and add the following line at the end:
```
@reboot /<path to the folder>/display.out
```
[WiringPi]: <https://github.com/orangepi-xunlong/wiringOP>
[armbian]: <https://www.armbian.com/>
