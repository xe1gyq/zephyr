# Build System User Guide

```bash
user@workstation:~$ source ~/.zephyrrc
user@workstation:~$ cd zephyr-project/
user@workstation:~/zephyr-project$ ls
arch         doc      fs       Kconfig         lib          Makefile      net      tests
boards       drivers  include  Kconfig.zephyr  LICENSE      Makefile.inc  samples  usb
defaults.tc  ext      Kbuild   kernel          MAINTAINERS  misc          scripts  zephyr-env.sh
user@workstation:~/zephyr-project$
```

## Make Menuconfig

```bash
user@workstation:~/zephyr-project$ make menuconfig
    ...
    Architecture (x86 architecture)
    x86 SoC Selection (Generic IA32 SoC)
    x86 Options
    Board Selection (QEMU x86)
    Board Options
    Kernel Type (Micro Kernel)
    General Kernel Options
    Nanokernel Options
    Microkernel Options
    Power Management
    Device Drivers
    Networking
    Cryptography
    Compile and Link Features
    Debugging Options
    Logging Options
    System Monitoring Options
    Boot Options
    Cryptography
    IoT Protocols
    File System
```

