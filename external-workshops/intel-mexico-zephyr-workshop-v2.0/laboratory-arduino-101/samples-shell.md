# Samples Shell

```bash
user@workstation:~/zephyr-project$ ls
arch    drivers  Kbuild          kernel   MAINTAINERS   misc     scripts
boards  ext      Kconfig         lib      Makefile      net      tests
doc     include  Kconfig.zephyr  LICENSE  Makefile.inc  samples  zephyr-env.sh
user@workstation:~/zephyr-project$ cd samples/shell/
user@workstation:~/zephyr-project/samples/shell$ ls
Makefile  prj.conf  src
user@workstation:~/zephyr-project/samples/shell$ cd src/
user@workstation:~/zephyr-project/samples/shell/src$ ls
main.c  Makefile
user@workstation:~/zephyr-project/samples/shell/src$
```

## Environment Checking

```bash
user@workstation:~/zephyr-project/samples/shell$ echo $ZEPHYR_BASE
/home/abraham/zephyr-project
user@workstation:~/zephyr-project/samples/shell$ echo $ZEPHYR_GCC_VARIANT
zephyr
user@workstation:~/zephyr-project/samples/shell$
```

## Application Template

```bash
user@workstation:~/zephyr-project/samples/shell$ ls -lhR 
.:
total 12K
-rw-rw-r-- 1 abraham abraham   95 jun 25 12:13 Makefile
-rw-rw-r-- 1 abraham abraham   72 jun 25 12:13 prj.conf
drwxrwxr-x 2 abraham abraham 4.0K jun 25 12:13 src

./src:
total 8.0K
-rw-rw-r-- 1 abraham abraham 1.4K jun 25 12:13 main.c
-rw-rw-r-- 1 abraham abraham   16 jun 25 12:13 Makefile
user@workstation:~/zephyr-project/samples/shell$
```

## Make Menuconfig

```bash
user@workstation:~/zephyr-project/samples/shell$ make menuconfig
make[1]: Entering directory `/home/abraham/zephyr-project'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/shell/outdir'
  GEN     ./Makefile
scripts/kconfig/mconf Kconfig


*** End of the configuration.
*** Execute 'make' to start the build or try 'make help'.

make[2]: Leaving directory `/home/abraham/zephyr-project/samples/shell/outdir'
make[1]: Leaving directory `/home/abraham/zephyr-project'
user@workstation:~/zephyr-project/samples/shell$
```

## Project Configuration

```bash
user@workstation:~/zephyr-project/samples/shell$ cat prj.conf 
CONFIG_CONSOLE_HANDLER=y
CONFIG_CONSOLE_HANDLER_SHELL=y
CONFIG_PRINTK=y
user@workstation:~/zephyr-project/samples/shell$
```

## Compilation

```bash
user@workstation:~/zephyr-project/samples/shell$ ls
Makefile  outdir  prj.conf  src
user@workstation:~/zephyr-project/samples/shell$ make BOARD=arduino_101_factory
Using /home/abraham/zephyr-project/boards/arduino_101/arduino_101_factory_defconfig as base
Merging /home/abraham/zephyr-project/kernel/configs/nano.config
Merging prj.conf
#
# configuration written to .config
#
make[1]: Entering directory `/home/abraham/zephyr-project'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/shell/outdir'
  GEN     ./Makefile
scripts/kconfig/conf --silentoldconfig Kconfig
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/shell/outdir'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/shell/outdir'
  Using /home/abraham/zephyr-project as source for kernel
  GEN     ./Makefile
  CHK     include/generated/version.h
  UPD     include/generated/version.h
  HOSTCC  scripts/gen_idt/gen_idt.o
  HOSTLD  scripts/gen_idt/gen_idt
  CHK     misc/generated/configs.c
  UPD     misc/generated/configs.c
  CHK     include/generated/offsets.h
  UPD     include/generated/offsets.h
  LD      lib/libc/minimal/source/stdlib/built-in.o
  CC      lib/libc/minimal/source/stdout/fprintf.o
  CC      lib/libc/minimal/source/stdout/prf.o
  CC      lib/libc/minimal/source/stdout/sprintf.o
  CC      lib/libc/minimal/source/stdout/stdout_console.o
  LD      lib/libc/minimal/source/stdout/built-in.o
  CC      lib/libc/minimal/source/string/string.o
  LD      lib/libc/minimal/source/string/built-in.o
  LD      lib/libc/minimal/source/built-in.o
  LD      lib/libc/minimal/built-in.o
  LD      lib/libc/built-in.o
  LD      lib/built-in.o
  CC      kernel/nanokernel/nano_fiber.o
  CC      kernel/nanokernel/nano_lifo.o
  CC      kernel/nanokernel/nano_fifo.o
  CC      kernel/nanokernel/nano_stack.o
  CC      kernel/nanokernel/nano_sys_clock.o
  CC      kernel/nanokernel/nano_context.o
  CC      kernel/nanokernel/nano_init.o
  CC      kernel/nanokernel/nano_sema.o
  CC      kernel/nanokernel/version.o
  CC      kernel/nanokernel/device.o
  CC      kernel/nanokernel/nano_timer.o
  CC      kernel/nanokernel/ring_buffer.o
  CC      kernel/nanokernel/errno.o
  LD      kernel/nanokernel/built-in.o
  LD      kernel/built-in.o
  CC      misc/printk.o
  LD      misc/debug/built-in.o
  CC      misc/generated/configs.o
  LD      misc/generated/built-in.o
  LD      misc/built-in.o
  LD      net/built-in.o
  CC      boards/arduino_101/pinmux.o
  CC      boards/arduino_101/board.o
  LD      boards/arduino_101/built-in.o
  LD      boards/built-in.o
  CC      arch/x86/core/iamcu_abi/swap.o
  CC      arch/x86/core/iamcu_abi/intstub.o
  CC      arch/x86/core/iamcu_abi/thread.o
  AS      arch/x86/core/iamcu_abi/iamcu.o
  LD      arch/x86/core/iamcu_abi/built-in.o
  CC      arch/x86/core/fatal.o
  CC      arch/x86/core/cpuhalt.o
  CC      arch/x86/core/msr.o
  CC      arch/x86/core/dynamic.o
  CC      arch/x86/core/intconnect.o
  CC      arch/x86/core/excconnect.o
  CC      arch/x86/core/sys_fatal_error_handler.o
  AS      arch/x86/core/crt0.o
  CC      arch/x86/core/atomic.o
  AS      arch/x86/core/cache_s.o
  CC      arch/x86/core/cache.o
  AS      arch/x86/core/excstub.o
  LD      arch/x86/core/built-in.o
  CC      arch/x86/soc/quark_se/soc.o
  CC      arch/x86/soc/quark_se/soc_config.o
  CC      arch/x86/soc/quark_se/eoi.o
  LD      arch/x86/soc/quark_se/built-in.o
  LD      arch/x86/built-in.o
  LD      arch/built-in.o
  CC      ext/hal/qmsi/drivers/clk.o
  CC      ext/hal/qmsi/drivers/qm_uart.o
  LD      ext/hal/qmsi/built-in.o
  LD      ext/hal/built-in.o
  LD      ext/lib/crypto/built-in.o
  LD      ext/lib/built-in.o
  LD      ext/built-in.o
  CC      drivers/console/console_handler_shell.o
  CC      drivers/console/uart_console.o
  CC      drivers/console/ipm_console_receiver.o
  LD      drivers/console/built-in.o
  CC      drivers/interrupt_controller/system_apic.o
  CC      drivers/interrupt_controller/loapic_intr.o
  CC      drivers/interrupt_controller/ioapic_intr.o
  LD      drivers/interrupt_controller/built-in.o
  CC      drivers/ipm/ipm_quark_se.o
  LD      drivers/ipm/built-in.o
  LD      drivers/pinmux/built-in.o
  LD      drivers/random/built-in.o
  CC      drivers/serial/uart_qmsi.o
  LD      drivers/serial/built-in.o
  CC      drivers/timer/loapic_timer.o
  CC      drivers/timer/sys_clock_init.o
  LD      drivers/timer/built-in.o
  LD      drivers/built-in.o
  CC      samples/shell/src/main.o
  LD      samples/shell/src/built-in.o
  LINK    zephyr.lnk
  SIDT    staticIdt.o
  LINK    zephyr.elf
  BIN     zephyr.bin
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/shell/outdir'
make[1]: Leaving directory `/home/abraham/zephyr-project'
user@workstation:~/zephyr-project/samples/shell$
```

## Kernel Dmesg

```bash
user@workstation:~/zephyr-project/samples/shell$ dmesg
...
[26110.263053] usb 3-1: new full-speed USB device number 8 using xhci_hcd
[26110.396749] usb 3-1: New USB device found, idVendor=0403, idProduct=6001
[26110.396752] usb 3-1: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[26110.396754] usb 3-1: Product: FT232R USB UART
[26110.396755] usb 3-1: Manufacturer: FTDI
[26110.396757] usb 3-1: SerialNumber: AL017LI9
[26110.399480] ftdi_sio 3-1:1.0: FTDI USB Serial Device converter detected
[26110.399510] usb 3-1: Detected FT232RL
[26110.399513] usb 3-1: Number of endpoints 2
[26110.399514] usb 3-1: Endpoint 1 MaxPacketSize 64
[26110.399515] usb 3-1: Endpoint 2 MaxPacketSize 64
[26110.399517] usb 3-1: Setting MaxPacketSize 64
[26110.399836] usb 3-1: FTDI USB Serial Device converter now attached to ttyUSB0
[29671.859244] usb 3-2: USB disconnect, device number 7
[29680.178952] usb 3-2: new full-speed USB device number 9 using xhci_hcd
[29680.369642] usb 3-2: New USB device found, idVendor=8087, idProduct=0aba
[29680.369647] usb 3-2: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[29680.369649] usb 3-2: Product: ARDUINO 101
[29680.369651] usb 3-2: Manufacturer: Intel
[29680.369653] usb 3-2: SerialNumber: AE6642SQ60400W3
user@workstation:~/zephyr-project/samples/shell$
```

## Flashing

```bash
user@workstation:~/zephyr-project/samples/shell$ sudo dfu-util -a x86_app -D outdir/zephyr.bin
[sudo] password for abraham:
```

```bash
dfu-util 0.7

Copyright 2005-2008 Weston Schmidt, Harald Welte and OpenMoko Inc.
Copyright 2010-2012 Tormod Volden and Stefan Schmidt
This program is Free Software and has ABSOLUTELY NO WARRANTY
Please report bugs to dfu-util@lists.gnumonks.org

No DFU capable USB device found
user@workstation:~/zephyr-project/samples/shell$
```

```bash
user@workstation:~/zephyr-project/samples/shell$ sudo dfu-util -a x86_app -D outdir/zephyr.bin
dfu-util 0.7

Copyright 2005-2008 Weston Schmidt, Harald Welte and OpenMoko Inc.
Copyright 2010-2012 Tormod Volden and Stefan Schmidt
This program is Free Software and has ABSOLUTELY NO WARRANTY
Please report bugs to dfu-util@lists.gnumonks.org

Opening DFU capable USB device... ID 8087:0aba
Run-time device DFU version 0011
Found DFU: [8087:0aba] devnum=0, cfg=1, intf=0, alt=2, name="x86_app"
Claiming USB DFU Interface...
Setting Alternate Setting #2 ...
Determining device status: state = dfuIDLE, status = 0
dfuIDLE, continuing
DFU mode device DFU version 0011
Device returned transfer size 2048
No valid DFU suffix signature
Warning: File has no DFU suffix
bytes_per_hash=349
Copying data from PC to DFU device
Starting download: [##################################################] finished!
state(2) = dfuIDLE, status(0) = No error condition is present
Done!
user@workstation:~/zephyr-project/samples/shell$
```

```bash
user@workstation:~$ screen /dev/ttyUSB0 115200
```

