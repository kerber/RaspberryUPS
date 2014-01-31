RaspberryUPS
============

Smart shutdown for the Raspberry Pi

This script will use a GPIO pin to trigger a shutdown after a grace period. To run this at startup, just add the following to /etc/rc.local before the **exit** line.

```bash
python /home/RaspberryUPS/power_monitor.py &
```

This code accompanies a quick hardware hack UPS for my Raspberry Pi. I found a handy little [rechargable battery pack](http://www.newegg.com/Product/Product.aspx?Item=N82E16875981375) on sale for $12. The important feature is that the output will stay active when the charging power is disconnected. To add auto-shutdown, the pack's 5v charging line is run through a voltage divider to make a safe 3.3v for the GPIO pin.
