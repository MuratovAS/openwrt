## Fork

Build:
```
cp .config-example .config
./scripts/feeds update -a && ./scripts/feeds install -a
make defconfig
make world
make kernel_menuconfig
make menuconfig
make -j8 V=s  
```

Note:
```
git format-patch -1 #create patch
git apply *.patch #apply patch
```

```
ethtool -i eth0 #driver info
```

Credit:
```
https://openwrt.org/docs/guide-user/additional-software/saving_space
https://github.com/matrixant/f1c200s_core
https://github.com/R4ynor/f1c200s
https://github.com/linyuxuanlin/Flip
https://github.com/xddcore/Zero_Linux_Board
https://github.com/embeddedboys/HamsterBear
https://github.com/YuzukiHD/YuzukiMavericks
https://github.com/mangopi-sbc/aw-doc
https://github.com/nminaylov/F1C100s_info
https://github.com/peng-zhihui/Planck-Pi
https://github.com/minilogic/f1c_dbc
https://github.com/matiko122/F1C100sDevBoard
https://github.com/serhaturtis/ES-SOM_F1C
https://github.com/JohnSanpe/neopi-nano
https://github.com/virtualwiz/NEKO-M5
https://github.com/mahdi2001h/SINUX_F1
https://github.com/kmakise/F1C100S_DB_R1
https://github.com/VeiLiang/BoloPi_PCB
https://github.com/voloviq/licheepinano_sarau270_lcd
https://linux-sunxi.org/Lctech_Pi_F1C200s
https://github.com/peng-zhihui/Planck-Pi

http://dl.sipeed.com/shareURL/LICHEE/Nano
https://github.com/wuxx/f1c100s-gpio-tools
https://github.com/nminaylov/F1C100s_projects

https://github.com/spidermanstruation/licheepi-nano-buildroot
https://github.com/unframework/lichee-kiosk
https://github.com/suda-morris/suda-f1c100s
https://github.com/kekemuyu/f1c100s
https://github.com/minilogic/f1c_nonos
https://github.com/newluhux/qemu-f1c100s
https://github.com/verylowfreq/buildroot-licheepi_nano
https://github.com/nand2mario/licheepi-nano-buildroot
https://github.com/unframework/licheepi-nano-buildroot
https://github.com/aodzip/buildroot-tiny200
https://github.com/TriForceX/MiyooCFW

https://github.com/uYanki/allwinner-chip-doc

https://programmerall.com/article/55812199675/

https://github.com/NateLol/luci-app-oled
https://wiki.kobol.io/helios4/i2c/

https://novi.kupujemprodajem.com/elektronika-i-komponente/moduli-za-samoizgradnju/mcp2515-can-bus-module-arduino/oglas/147840983?filterId=3912162720


https://github.com/HandsomeMod/HandsomeMod/blob/fa7f0be51858a64e0d5f9e1f1a3c6bdb137c3eba/target/linux/sunxi/patches-5.4/442-suniv-Add-DMA-Controller.patch
https://github.com/jockm/lichee-nano-one-key-package/blob/ebcad700aa613f22d67c9a49e5cef72f2cee4d0a/linux-suniv-f1c100s.dtsi#L262
https://github.com/jockm/lichee-nano-one-key-package/blob/master/linux-licheepi_nano_defconfig
https://github.com/unframework/licheepi-nano-buildroot/blob/master/board/licheepi_nano/licheepi_nano_linux_defconfig
https://github.com/torvalds/linux/commit/5c043901fef2ff9a8467e407eb5321857f7473bb
```

![OpenWrt logo](include/logo.png)

OpenWrt Project is a Linux operating system targeting embedded devices. Instead
of trying to create a single, static firmware, OpenWrt provides a fully
writable filesystem with package management. This frees you from the
application selection and configuration provided by the vendor and allows you
to customize the device through the use of packages to suit any application.
For developers, OpenWrt is the framework to build an application without having
to build a complete firmware around it; for users this means the ability for
full customization, to use the device in ways never envisioned.

Sunshine!

## Download

Built firmware images are available for many architectures and come with a
package selection to be used as WiFi home router. To quickly find a factory
image usable to migrate from a vendor stock firmware to OpenWrt, try the
*Firmware Selector*.

* [OpenWrt Firmware Selector](https://firmware-selector.openwrt.org/)

If your device is supported, please follow the **Info** link to see install
instructions or consult the support resources listed below.

## 

An advanced user may require additional or specific package. (Toolchain, SDK, ...) For everything else than simple firmware download, try the wiki download page:

* [OpenWrt Wiki Download](https://openwrt.org/downloads)

## Development

To build your own firmware you need a GNU/Linux, BSD or MacOSX system (case
sensitive filesystem required). Cygwin is unsupported because of the lack of a
case sensitive file system.

### Requirements

You need the following tools to compile OpenWrt, the package names vary between
distributions. A complete list with distribution specific packages is found in
the [Build System Setup](https://openwrt.org/docs/guide-developer/build-system/install-buildsystem)
documentation.

```
binutils bzip2 diff find flex gawk gcc-6+ getopt grep install libc-dev libz-dev
make4.1+ perl python3.6+ rsync subversion unzip which
```

### Quickstart

1. Run `./scripts/feeds update -a` to obtain all the latest package definitions
   defined in feeds.conf / feeds.conf.default

2. Run `./scripts/feeds install -a` to install symlinks for all obtained
   packages into package/feeds/

3. Run `make menuconfig` to select your preferred configuration for the
   toolchain, target system & firmware packages.

4. Run `make` to build your firmware. This will download all sources, build the
   cross-compile toolchain and then cross-compile the GNU/Linux kernel & all chosen
   applications for your target system.

### Related Repositories

The main repository uses multiple sub-repositories to manage packages of
different categories. All packages are installed via the OpenWrt package
manager called `opkg`. If you're looking to develop the web interface or port
packages to OpenWrt, please find the fitting repository below.

* [LuCI Web Interface](https://github.com/openwrt/luci): Modern and modular
  interface to control the device via a web browser.

* [OpenWrt Packages](https://github.com/openwrt/packages): Community repository
  of ported packages.

* [OpenWrt Routing](https://github.com/openwrt/routing): Packages specifically
  focused on (mesh) routing.

* [OpenWrt Video](https://github.com/openwrt/video): Packages specifically
  focused on display servers and clients (Xorg and Wayland).

## Support Information

For a list of supported devices see the [OpenWrt Hardware Database](https://openwrt.org/supported_devices)

### Documentation

* [Quick Start Guide](https://openwrt.org/docs/guide-quick-start/start)
* [User Guide](https://openwrt.org/docs/guide-user/start)
* [Developer Documentation](https://openwrt.org/docs/guide-developer/start)
* [Technical Reference](https://openwrt.org/docs/techref/start)

### Support Community

* [Forum](https://forum.openwrt.org): For usage, projects, discussions and hardware advise.
* [Support Chat](https://webchat.oftc.net/#openwrt): Channel `#openwrt` on **oftc.net**.

### Developer Community

* [Bug Reports](https://bugs.openwrt.org): Report bugs in OpenWrt
* [Dev Mailing List](https://lists.openwrt.org/mailman/listinfo/openwrt-devel): Send patches
* [Dev Chat](https://webchat.oftc.net/#openwrt-devel): Channel `#openwrt-devel` on **oftc.net**.

## License

OpenWrt is licensed under GPL-2.0
