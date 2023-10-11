## MangoPI R3 board (Allwinner F1C200s chip)

### Direction for use
- After powering on the board, you can connect to the console through the TTL USB port
- Or use the usb-ttl tool to connect `PA2` and `PA3` to the console

### Peripheral support
| **Peripheral** |               **Describe**               |
|----------------|------------------------------------------|
|   USB OTG      | MTD Devices                              |
|   USB TTL      | uart1 console                            |
|     UART       | uart0 to uart2                           |
| Display Engine | Frontend, Backend, TCON                  |
|      I2C       | Connect to touch                         |
|      SPI       | Nor / Nand Flash                         |
|  DVP Camera    | OV2640 / OV5640                          |
|      SDIO      | TF Card slot                             |

### Build
```
# Using mangopi_r3_defconfig
make mangopi_r3_defconfig

# Start compiling the tf card image
make
```

### Reference
https://github.com/mangopi-sbc/buildroot-mangopi-r
