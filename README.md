# erofs-huawei-extension

## Apply patch

### Gentoo

```sh
# git clone https://github.com/ud3v0id/erofs-huawei-extension ~/
# mkdir -p /etc/portage/patches/sys-kernel/
# cp -r ~/erofs-huawei-extension/gentoo-sources-* /etc/portage/patches/sys-kernel/
# emerge gentoo-sources
```

### Other Linux

```sh
# git clone https://github.com/ud3v0id/erofs-huawei-extension ~/
# cd /usr/src/linux
# git apply ~/erofs-huawei-extension/gentoo-sources-{kernel version}/*
```

## Activate kernel options

### Kernel 5.4 and later

```
File systems  --->
  [*] Miscellaneous filesystems  --->
    <M>   EROFS filesystem support
    [*]     EROFS extended attributes
    [*]       EROFS Access Control Lists
    [*]       EROFS Security Labels
    [*]     EROFS Data Compresssion Support
    (1)       EROFS Cluster Pages Hard Limit
    [*]       EROFS HUAWEI Extension
```

### Kernel 5.4 before

```
Device Drivers  --->
  Staging drivers  --->
    <M>   EROFS filesystem support
    [*]     EROFS extended attributes
    [*]       EROFS Access Control Lists
    [*]       EROFS Security Labels
    [*]     EROFS Data Compresssion Support
    (1)       EROFS Cluster Pages Hard Limit
    [*]       EROFS HUAWEI Extension
```

## Build

Reference [Kernel Build](https://wiki.gentoo.org/wiki/Kernel/Configuration#Build)

## Usage

```sh
# mount -t erofs -o loop system.raw system/
```
