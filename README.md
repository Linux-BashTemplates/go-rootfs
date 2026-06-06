# go-rootfs
Minimal rootfs environment for Go development.

## Installation

```bash
wget -L -O devtools-x86_64.tar.xz https://github.com/Linux-BashTemplates/go-rootfs/releases/download/image/devtools-x86_64.tar.xz
mkdir -p ~/devtools
tar -xvf devtools-x86_64.tar.xz -C ~/devtools/
```
## Give root access into your system  

```bash
sudo su
```
## Mount the required filesystems:

```bash
mount -t proc proc ~/devtools/proc
mount -t sysfs sys ~/devtools/sys
mount --bind /dev ~/devtools/dev
mount --bind /dev/pts ~/devtools/dev/pts

```

Enter the environment:

```bash
chroot ~/devtools /bin/login -f root
mount --bind /dev/shm ./dev/shm
```

## Cleanup

After exiting the chroot environment:

```bash
umount ~/devtools/dev/pts
umount ~/devtools/dev
umount ~/devtools/proc
umount ~/devtools/sys
```

## Base system

This rootfs is based on Alpine Linux.

Alpine Linux is a lightweight Linux distribution:
https://alpinelinux.org/

This project does not modify Alpine Linux licensing terms and respects its original license. 

## Tags
`go` `golang` `rootfs` `chroot` `linux` `development` `toolchain` `build-environment` `minimal-linux` `cross-platform`
