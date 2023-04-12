## MangoPI MQ-Quad board (Allwinner H616 chip)

### Direction for use
- Modify the `board/mangopi_mq-quad/rootfs/etc/wpa_supplicant/wpa_supplicant-wlan0.conf` file, Set the WiFi ssid and password
- Using `systemctrl start wpa_supplicant@wlan0` command to connect Wifi
- Using `systemctrl enable wpa_supplicant@wlan0` Automatic startup connection
- After powering on the board, you can connect to the console through the analog serial port of the OTG typec port
- Or connect HDMI and keyboard for console interaction.

### Peripheral support
| **Peripheral** |               **Describe**               |
|----------------|------------------------------------------|
|   RTL8723DS    | WiFi/BT                                  |
|   USB Host     | 1 typec host with2 usb host in misc port |
|   USB OTG      | 1 typec otg                              |
|   ethernet     | ethernet for mac1 with ephy in misc port |
|     UART       | uart1 with uart2                         |
|  Mini HDMI     | hdmi with audio                          |
|      I2C       | i2c1 with i2c2                           |
|  Nor Flash     | spi0 nor flash                           |
|      SPI       | spi1dev drivers                          |
|      GPU       | gpu(panforst)                            |

### Build
```
# Using mangopi_mq_quad_defconfig
make mangopi_mq_quad_defconfig

# Start compiling the tf card image
make
```

### Reference
https://github.com/open-cores/mangguo-h616-armbian
