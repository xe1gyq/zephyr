# Arduino 101

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
user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello_world/microkernel$ make pristine && make BOARD=arduino_101
Using /home/user/Intel/Zephyr/zephyr-project/boards/arduino_101/arduino_101_defconfig as base
Merging /home/user/Intel/Zephyr/zephyr-project/kernel/configs/micro.config
Merging prj.conf
#
# configuration written to .config
#
make[1]: se ingresa al directorio «/home/user/Intel/Zephyr/zephyr-project»
make[2]: se ingresa al directorio «/home/user/Intel/Zephyr/zephyr-project/samples/hello_world/microkernel/outdir/arduino_101»
  GEN     ./Makefile
scripts/kconfig/conf --silentoldconfig Kconfig
make[2]: se sale del directorio «/home/user/Intel/Zephyr/zephyr-project/samples/hello_world/microkernel/outdir/arduino_101»
make[2]: se ingresa al directorio «/home/user/Intel/Zephyr/zephyr-project/samples/hello_world/microkernel/outdir/arduino_101»
  Using /home/user/Intel/Zephyr/zephyr-project as source for kernel
  GEN     ./Makefile
  CHK     include/generated/version.h
  UPD     include/generated/version.h
  HOSTCC  scripts/gen_idt/gen_idt.o
  HOSTLD  scripts/gen_idt/gen_idt
  CHK     misc/generated/configs.c
  UPD     misc/generated/configs.c
  CHK     include/generated/offsets.h
  UPD     include/generated/offsets.h
  CHK     misc/generated/sysgen/prj.mdef
  UPD     misc/generated/sysgen/prj.mdef
  LD      lib/iot/built-in.o
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
  CC      kernel/microkernel/k_task.o
  CC      kernel/microkernel/k_idle.o
  CC      kernel/microkernel/k_init.o
  CC      kernel/microkernel/k_command_packet.o
  CC      kernel/microkernel/k_move_data.o
  CC      kernel/microkernel/k_ticker.o
  CC      kernel/microkernel/k_memory_map.o
  CC      kernel/microkernel/k_memory_pool.o
  CC      kernel/microkernel/k_nop.o
  CC      kernel/microkernel/k_offload.o
  CC      kernel/microkernel/k_event.o
  CC      kernel/microkernel/k_mailbox.o
  CC      kernel/microkernel/k_mutex.o
  CC      kernel/microkernel/k_fifo.o
  CC      kernel/microkernel/k_semaphore.o
  CC      kernel/microkernel/k_timer.o
  CC      kernel/microkernel/k_pipe_buffer.o
  CC      kernel/microkernel/k_pipe.o
  CC      kernel/microkernel/k_pipe_get.o
  CC      kernel/microkernel/k_pipe_put.o
  CC      kernel/microkernel/k_pipe_util.o
  CC      kernel/microkernel/k_pipe_xfer.o
  CC      kernel/microkernel/k_nano.o
  CC      kernel/microkernel/k_server.o
  LD      kernel/microkernel/built-in.o
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
  CC      kernel/nanokernel/wait_q.o
  CC      kernel/nanokernel/errno.o
  LD      kernel/nanokernel/built-in.o
  LD      kernel/built-in.o
  CC      misc/printk.o
  LD      misc/debug/built-in.o
  CC      misc/generated/configs.o
  CC      misc/generated/sysgen/kernel_main.o
  LD      misc/generated/sysgen/built-in.o
  LD      misc/generated/built-in.o
  LD      misc/built-in.o
  LD      net/built-in.o
  CC      boards/arduino_101/pinmux.o
  LD      boards/arduino_101/built-in.o
  LD      boards/built-in.o
  LD      ext/fs/built-in.o
  CC      ext/hal/qmsi/drivers/flash/qm_flash.o
  CC      ext/hal/qmsi/soc/quark_se/drivers/power_states.o
  CC      ext/hal/qmsi/soc/quark_se/drivers/clk.o
  CC      ext/hal/qmsi/soc/quark_se/drivers/vreg.o
  CC      ext/hal/qmsi/drivers/uart/qm_uart.o
  LD      ext/hal/qmsi/built-in.o
  LD      ext/hal/built-in.o
  LD      ext/lib/crypto/built-in.o
  LD      ext/lib/built-in.o
  LD      ext/built-in.o
  LD      usb/built-in.o
  LD      fs/built-in.o
  LD      tests/built-in.o
  CC      arch/x86/core/cpuhalt.o
  CC      arch/x86/core/msr.o
  CC      arch/x86/core/irq_manage.o
  CC      arch/x86/core/sys_fatal_error_handler.o
  AS      arch/x86/core/crt0.o
  AS      arch/x86/core/cache_s.o
  CC      arch/x86/core/cache.o
  AS      arch/x86/core/excstub.o
  AS      arch/x86/core/intstub.o
  AS      arch/x86/core/swap.o
  CC      arch/x86/core/thread.o
  CC      arch/x86/core/strtask.o
  CC      arch/x86/core/fatal.o
  LD      arch/x86/core/built-in.o
  CC      arch/x86/soc/intel_quark/quark_se/soc.o
  CC      arch/x86/soc/intel_quark/quark_se/soc_config.o
  CC      arch/x86/soc/intel_quark/quark_se/eoi.o
  CC      arch/x86/soc/intel_quark/quark_se/power.o
  AS      arch/x86/soc/intel_quark/quark_se/soc_power.o
  LD      arch/x86/soc/intel_quark/quark_se/built-in.o
  LD      arch/x86/built-in.o
  LD      arch/built-in.o
  CC      drivers/console/uart_console.o
  LD      drivers/console/built-in.o
  CC      drivers/interrupt_controller/loapic_intr.o
  CC      drivers/interrupt_controller/system_apic.o
  CC      drivers/interrupt_controller/ioapic_intr.o
  LD      drivers/interrupt_controller/built-in.o
  LD      drivers/pinmux/built-in.o
  LD      drivers/random/built-in.o
  CC      drivers/serial/uart_qmsi.o
  LD      drivers/serial/built-in.o
  CC      drivers/timer/loapic_timer.o
  CC      drivers/timer/sys_clock_init.o
  LD      drivers/timer/built-in.o
  LD      drivers/built-in.o
  CC      src/main.o
  LD      src/built-in.o
  AR      libzephyr.a
  LINK    zephyr.lnk
  SIDT    staticIdt.o
  LINK    zephyr.elf
  BIN     zephyr.bin
make[2]: se sale del directorio «/home/user/Intel/Zephyr/zephyr-project/samples/hello_world/microkernel/outdir/arduino_101»
make[1]: se sale del directorio «/home/user/Intel/Zephyr/zephyr-project»
user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello_world/microkernel$
```

```bash
user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello_world/microkernel$ sudo dfu-util -a x86_app -D outdir/arduino_101/zephyr.bin 
sudo: imposible resolver el anfitrión workstation
dfu-util 0.5

(C) 2005-2008 by Weston Schmidt, Harald Welte and OpenMoko Inc.
(C) 2010-2011 Tormod Volden (DfuSe support)
This program is Free Software and has ABSOLUTELY NO WARRANTY

dfu-util does currently only support DFU version 1.0

Opening DFU USB device... ID 8087:0aba
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
bytes_per_hash=248
Copying data from PC to DFU device
Starting download: [##################################################] finished!
state(2) = dfuIDLE, status(0) = No error condition is present
Done!
user@workstation:~/Intel/Zephyr/zephyr-project/samples/hello_world/microkernel$
```

