# go-rootfs
Ready-to-use root filesystem containing Go compiler, Go Modules support, build tools, debuggers, and utilities for Go software development.

# go-rootfs

Minimal rootfs environment for Go development.

## Installation

```bash
mkdir -p ~/devtools
tar -xvf devtools-x86_64.tar.xz -C ~/devtools/
```

## Runnable

Mount the required filesystems:

```bash
sudo mount -t proc proc ~/devtools/proc
sudo mount -t sysfs sys ~/devtools/sys
sudo mount --bind /dev ~/devtools/dev
sudo mount --bind /dev/pts ~/devtools/dev/pts
```

Enter the environment:

```bash
sudo chroot ~/devtools /bin/login -f root
```

## Cleanup

After exiting the chroot environment:

```bash
sudo umount ~/devtools/dev/pts
sudo umount ~/devtools/dev
sudo umount ~/devtools/proc
sudo umount ~/devtools/sys
```

## Tags

`go` `golang` `rootfs` `chroot` `linux` `development` `toolchain` `build-environment` `minimal-linux` `cross-platform`
