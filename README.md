U-Boot modification for NEXX WT3020
==========

Introduction
------------

In short, this project is a modification of **U-Boot** sources for MediaTek SoC.

The concept for this project came from another U-Boot modification, dedicated to a small and very popular TP-Link router - model **TL-WR703N**, which includes web fail safe mode: **[wr703n-uboot-with-web-failsafe](http://code.google.com/p/wr703n-uboot-with-web-failsafe/)**.

Supported device
----------------

Currently supported devices:

- **MediaTek MT7620**:
  - NEXX WT3020

Modifications, changes
----------------------

### Web server

The most important change is an inclusion of a web server, based on uIP 0.9 TCP/IP stack. It allows to upgrade **firmware**, **U-Boot** and **ART** (Atheros Radio Test) images, directly from your web browser, without need to access serial console and running a TFTP server.

Web server contains 7 pages:

1. index.html (allows to upgrade firmware image)
2. uboot.html (allows to upgrade U-Boot image)
3. art.html (allows to upgrade ART image)
4. flashing.html
5. 404.html
6. fail.html
7. style.css

How to compile the code
-----------------------

You need to install **[openjdk-7-jre](http://openjdk.java.net/)** and toolchain (buildroot-gcc342), contained in one of the below SDK, to `/opt/`:

- MTK_Ralink_ApSoC_SDK_4110
- MTK_Ralink_ApSoC_SDK_4200
- MTK_Ralink_ApSoC_SDK_4210

To build image, run:

```
make menuconfig (-> Load WT3020)
make
```

License, outdated sources etc.
------------------------------

**[U-Boot](http://www.denx.de/wiki/U-Boot/WebHome)** project is Free Software, licensed under version 2 of the **GNU General Public License**.

Credits
-------

- Thanks to pepe2k for [u-boot_mod](https://github.com/pepe2k/u-boot_mod)
- Thanks to cleanwrt for [u-boot_mt7620](https://github.com/cleanwrt/u-boot_mt7620)
