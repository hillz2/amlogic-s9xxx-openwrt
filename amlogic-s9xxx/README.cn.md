# Amlogic s9xxx 系列相关文件说明

查看英文说明 | [View English description](README.md)

在相关目录中存储了一些与 Amlogic s9xxx 内核相关的编译 OpenWrt 所需的文件。

## amlogic-armbian

这里存放的文件是打包 OpenWrt 时需要使用的 Armbian 的相关文件。

## amlogic-dtb

这里收录了各种型号机顶盒使用的 .dtb 文件，当你在使用安装脚本 [openwrt-install-amlogic](https://github.com/ophub/amlogic-s9xxx-openwrt/blob/main/amlogic-s9xxx/common-files/files/usr/sbin/openwrt-install-amlogic) 将 OpenWrt 写入 EMMC 时，当你选择 0 进行自选 .dtb 文件安装时，需要填写具体的 .dtb 文件名称，你可以从这里查阅准确的文件名并填写，具体参见 [amlogic-dtb](https://github.com/ophub/amlogic-s9xxx-openwrt/tree/main/amlogic-s9xxx/amlogic-dtb)

## amlogic-kernel

在 `amlogic-kernel` 目录下存放的是编译 OpenWrt 需要的内核文件，使用方法见 [amlogic-kernel/README.md](amlogic-kernel/README.md)

## amlogic-u-boot

当你使用 5.10 内核的 OpenWrt 时，需要将 u-boot 文件复制为 `u-boot.ext` ，在 EMMC 中使用时，需要将 u-boot 文件复制为 `u-boot.emmc` 。这些复制工作在仓库的打包和安装/升级脚本中均已自动化完成，无需在人工复制。各型号对应的具体文件详见 [u-boot-*.bin](https://github.com/ophub/amlogic-s9xxx-openwrt/tree/main/amlogic-s9xxx/amlogic-u-boot)

## common-files

- files: 这里存放的是 OpenWrt 固件的个性化配置文件，将在打包脚本 `sudo ./make` 执行时自动将相关文件集成到你的固件里。相关目录及文件命名均须与 OpenWrt 中 ROOTFS 分区 ( 即在 TTYD 终端里输入： `cd / && ls .` 你所看到的目录及各目录里面的文件名称 ) 保持完全一致。

```yaml
etc/config/amlogic
usr/sbin
```

- patches: 这是补丁文件存放目录，你可以将扩展文件，魔改补丁等放置在该目录。具有详见 [patches](https://github.com/ophub/amlogic-s9xxx-openwrt/tree/main/amlogic-s9xxx/common-files/patches)

