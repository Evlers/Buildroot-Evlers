## Buildroot-Evlers
Based on buildroot-2023.02<br>
Removes all original boards and adds new board support
<br>

### Support board list
Note: Click the corresponding board to view the peripheral support or descriptions.
|   **Manufacturer**    |                   **Board**                       |           **defconfig**           |             **Describe**                  |
|-----------------------|---------------------------------------------------|-----------------------------------|-------------------------------------------|
|   MangoPI             |   [MQ-Quad](./board/mangopi/mq-quad/README.md)    |   mangopi_mq_quad_defconfig       |   Base on Allwinner H616                  |
|   MangoPI             |   MQ-Dual                                         |   ~~mangopi_mq_dual_defconfig~~   |   Base on Allwinner T113-S3               |
|   MangoPI             |   R3                                              |   ~~mangopi_r3_defconfig~~        |   Base on Allwinner F1C200s               |
|   Alientek            |   STM32MP157                                      |   ~~alientek_mp157_defconfig~~    |   Base on STMicroelectronics STM32MP157   |


### Get started quickly
```
# Select the corresponding defconfig configuration file, For example: MangoPI MQ-Quad board
make mangopi_mq_quad_defconfig

# Build and pack to output/images
make 
```

### Directory structure
MangoPI MQ-Quad board example base on Allwinner H616:
```
├── configs                                         # buildroot configuration for each board
└── board                                           # Board or chip file
    ├── allwinner                                   # The configuration of the Allwinner chip
    │   ├── generic                                 # Generic file
    │   │   ├── genimage_sdcard.cfg                 # Configuration for generating TF card images files
    │   │   └── post-build.sh                       # A script to execute after compiling
    │   └── H616                                    # Allwinner H616 chip configs
    │       ├── devicetree                          # The device tree for the chip
    │       │   ├── linux                           # device tree for linux
    │       │   └── uboot                           # device tree for u-boot
    │       ├── patches                             # The patch for the chip
    │       │   ├── linux                           # patch for linux kernel
    │       │   └── uboot                           # patch for u-boot
    │       └── rootfs                              # The rootfs for the chip (overwrite)
    └── mangopi                                     # The configuration of the MangoPI series board
        └── mq-quad                                 # The configuration of the MangoPI MQ-Quad board
            ├── boot.cmd                            # u-boot command configuration of the boot kernel
            ├── configs                             # The board configuration file for linux and u-boot
            │   ├── linux_defconfig                 # Linux kernel config file
            │   └── uboot_defconfig                 # u-boot config file
            ├── devicetree                          # The device tree for the board
            │   ├── linux                           # device tree for linux
            │   └── uboot                           # device tree for u-boot
            ├── README.md                           # The description of the board
            └── rootfs                              # The rootfs for the board (overwrite)
```

### About buildroot
```
Buildroot is a simple, efficient and easy-to-use tool to generate embedded
Linux systems through cross-compilation.

The documentation can be found in docs/manual. You can generate a text
document with 'make manual-text' and read output/docs/manual/manual.text.
Online documentation can be found at http://buildroot.org/docs.html

To build and use the buildroot stuff, do the following:

1) run 'make menuconfig'
2) select the target architecture and the packages you wish to compile
3) run 'make'
4) wait while it compiles
5) find the kernel, bootloader, root filesystem, etc. in output/images

You do not need to be root to build or run buildroot.  Have fun!

Buildroot comes with a basic configuration for a number of boards. Run
'make list-defconfigs' to view the list of provided configurations.

Please feed suggestions, bug reports, insults, and bribes back to the
buildroot mailing list: buildroot@buildroot.org
You can also find us on #buildroot on OFTC IRC.

If you would like to contribute patches, please read
https://buildroot.org/manual.html#submitting-patches

```
