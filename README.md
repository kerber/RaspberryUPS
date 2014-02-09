RaspberryUPS
============

The RaspberryUPS service monitors a GPIO pin to trigger a shutdown after a grace period. In conjunction with a USB battery pack, it makes for a great Uninterruptable Power Supply for the Raspberry Pi.

To set up the service:

1. Edit RaspberryUPS
  * Set DIR to the checkout directory.
2. Edit power_monitor.py
  * Set SHUTDOWN_GRACE to the number of minutes to wait before shutting down.
  * Set POWER_PIN to the GPIO pin connected to the power detect line
3. Set RaspberryUPS and power_monitor.py to executable.
4. Copy the RaspberryUPS file to /etc/init.d/RaspberryUPS

Now, start the process with:

```bash
service RaspberryUPS start
```

For the harware side, find a USB rechargale battery pack that will provide output power while it is charging. It is also important that the output stay active when the charging power is disconnected. Many battery packs require you press a power button, so pay attention. I was able to snag [one on sale for $12](http://www.newegg.com/Product/Product.aspx?Item=N82E16875981375). To add auto-shutdown, the pack's 5v charging line is run through a voltage divider to make a safe 3.3v for the GPIO pin. This is important, as 5v will kill your Raspberry Pi.
