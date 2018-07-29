# Galileo Gen1/Gen2

## Intel Galileo

## Official Documentation

* [Zephyr Project Galileo Gen1 Gen2](https://wiki.zephyrproject.org/view/Galileo_Gen1_Gen2)

## Creating a GRUB2 Boot Loader Image from a Linux Host

```bash
user@workstation:~$ sudo apt-get install bison autoconf libopts25-dev flex automake
```

```bash
user@workstation:~$ cd ~/Intel/Zephyr/zephyr-project/
user@workstation:~/Intel/Zephyr/zephyr-project$ ls
arch         doc      fs       Kconfig         lib          Makefile      net      tests
boards       drivers  include  Kconfig.zephyr  LICENSE      Makefile.inc  samples  usb
defaults.tc  ext      Kbuild   kernel          MAINTAINERS  misc          scripts  zephyr-env.sh
user@workstation:~/Intel/Zephyr/zephyr-project$ source zephyr-env.sh 
user@workstation:~/Intel/Zephyr/zephyr-project$
```

```bash
user@workstation:~$ cd $ZEPHYR_BASE
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project$ ls
arch         doc      fs       Kconfig         lib          Makefile      net      tests
boards       drivers  include  Kconfig.zephyr  LICENSE      Makefile.inc  samples  usb
defaults.tc  ext      Kbuild   kernel          MAINTAINERS  misc          scripts  zephyr-env.sh
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project$ ./scripts/build_grub.sh
...
...
~/Intel/Zephyr/zephyr-project/scripts/grub ~/Intel/Zephyr/zephyr-project
~/Intel/Zephyr/zephyr-project
```

### Preparing the Boot Device

```bash
user@workstation:~/Intel/Zephyr/zephyr-project$ dmesg
...
...
[470637.182794] mmc0: new SD card at address e624
[470637.188637] mmcblk0: mmc0:e624 SU01G 968 MiB 
[470637.189523]  mmcblk0: p1
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project$ sudo mkdir /media/sdcard
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project$ sudo mount -t vfat /dev/mmcblk0p1 /media/sdcard/
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello_world/nanokernel$ mkdir /media/sdcard/efi
user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello_world/nanokernel$ mkdir /media/sdcard/efi/boot
user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello_world/nanokernel$ mkdir /media/sdcard/kernel
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project$ cp outdir/galileo/zephyr.strip /media/sdcard/kernel/
user@workstation:~/Intel/Zephyr/zephyr-project$ cp ../../../scripts/grub/bin/grub.efi /media/sdcard/efi/boot/bootia32.efi
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project$ nano /media/sdcard/efi/boot/grub.cfg
```

```bash
set default=0
set timeout=10

menuentry "Zephyr Kernel" {
   multiboot /kernel/zephyr.strip
}
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project$ sudo umount /dev/mmcblk0p1
```

### Building

```bash
user@workstation:~$ cd zephyr-project/
user@workstation:~/Intel/Zephyr/zephyr-project$ ls
arch         doc      fs       Kconfig         lib          Makefile      net      tests
boards       drivers  include  Kconfig.zephyr  LICENSE      Makefile.inc  samples  usb
defaults.tc  ext      Kbuild   kernel          MAINTAINERS  misc          scripts  zephyr-env.sh
user@workstation:~/Intel/Zephyr/zephyr-project$ source zephyr-env.sh 
user@workstation:~/Intel/Zephyr/zephyr-project$
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project$ cd samples/hello_world/nanokernel/
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello_world/nanokernel$ make pristine && make BOARD=galileo
...
...
  LINK    zephyr.lnk
  SIDT    staticIdt.o
  LINK    zephyr.elf
  BIN     zephyr.bin
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello_world/nanokernel$ ls outdir/galileo/
arch     ext               include               kernel       linker.cmd  net      staticIdt.o  zephyr.elf  zephyr.map
boards   final-linker.cmd  int_vector_alloc.o    lib          Makefile    scripts  usb          zephyr.lnk  zephyr.stat
drivers  fs                irq_int_vector_map.o  libzephyr.a  misc        src      zephyr.bin   zephyr.lst  zephyr.strip
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello_world/nanokernel$ file outdir/galileo/zephyr.strip 
outdir/galileo/zephyr.strip: ELF 32-bit LSB  executable, Intel 80386, version 1 (SYSV), statically linked, stripped
```

### Booting the Galileo Board

```bash
    Press [Enter] to directly boot.
    Press [F7]    to show boot menu options.
```

```bash
    Booting `Zephyr Kernel'
    WARNING: no console will be available to OS
    error: no suitable video mode found.
```

user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello\_world/nanokernel$ Let´s Get To Work

