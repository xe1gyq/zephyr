# Building and Running an Application

## Download the Code

```bash
user@workstation:~$ git config --global --unset http.proxy
user@workstation:~$ git config --global --unset https.proxy
```

```bash
user@workstation:~$ git clone https://gerrit.zephyrproject.org/r/zephyr zephyr-project
Cloning into 'zephyr-project'...
remote: Counting objects: 3, done
remote: Finding sources: 100% (3/3)
remote: Total 60526 (delta 0), reused 60526 (delta 0)
Receiving objects: 100% (60526/60526), 19.74 MiB | 1.09 MiB/s, done.
Resolving deltas: 100% (40213/40213), done.
Checking connectivity... done.
```

## Setting the Project’s Environment Variables

```bash
user@workstation:~$ source ~/.zephyrrc
user@workstation:~$ cd zephyr-project/
user@workstation:~/zephyr-project$ ls
arch         doc      fs       Kconfig         lib          Makefile      net      tests
boards       drivers  include  Kconfig.zephyr  LICENSE      Makefile.inc  samples  usb
defaults.tc  ext      Kbuild   kernel          MAINTAINERS  misc          scripts  zephyr-env.sh
user@workstation:~/zephyr-project$ source zephyr-env.sh 
user@workstation:~/zephyr-project$
```

## Building and Running an Application

```bash
user@workstation:~/zephyr-project$ cd $ZEPHYR_BASE/samples/hello_world/microkernel
user@workstation:~/zephyr-project/samples/hello_world/microkernel$ make BOARD=galileo
Using /home/abraham/zephyr-project/boards/galileo/galileo_defconfig as base
Merging /home/abraham/zephyr-project/kernel/configs/micro.config
Merging prj.conf
#
# configuration written to .config
#
make[1]: Entering directory `/home/abraham/zephyr-project'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/hello_world/microkernel/outdir'
  GEN     ./Makefile
scripts/kconfig/conf --silentoldconfig Kconfig
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/hello_world/microkernel/outdir'
make[2]: Entering directory `/home/abraham/zephyr-project/samples/hello_world/microkernel/outdir'
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
  CHK     misc/generated/sysgen/prj.mdef
  UPD     misc/generated/sysgen/prj.mdef
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
  CC      kernel/microkernel/k_irq.o
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
  CC      kernel/nanokernel/nano_sleep.o
  CC      kernel/nanokernel/nano_timer.o
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
  CC      boards/galileo/board.o
  CC      boards/galileo/pinmux.o
  LD      boards/galileo/built-in.o
  LD      boards/built-in.o
  AS      arch/x86/core/i386_sysV_abi/intstub.o
  AS      arch/x86/core/i386_sysV_abi/swap.o
  CC      arch/x86/core/i386_sysV_abi/thread.o
  LD      arch/x86/core/i386_sysV_abi/built-in.o
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
  CC      arch/x86/core/strtask.o
  LD      arch/x86/core/built-in.o
  CC      arch/x86/soc/quark_x1000/soc.o
  LD      arch/x86/soc/quark_x1000/built-in.o
  LD      arch/x86/built-in.o
  LD      arch/built-in.o
  LD      ext/hal/built-in.o
  LD      ext/lib/crypto/built-in.o
  LD      ext/lib/built-in.o
  LD      ext/built-in.o
  CC      drivers/adc/adc_ti_adc108s102.o
  LD      drivers/adc/built-in.o
  CC      drivers/console/uart_console.o
  LD      drivers/console/built-in.o
  CC      drivers/gpio/gpio_api_compat.o
  CC      drivers/gpio/gpio_dw.o
  CC      drivers/gpio/gpio_pcal9535a.o
  CC      drivers/gpio/gpio_sch.o
  LD      drivers/gpio/built-in.o
  CC      drivers/i2c/i2c_dw.o
  LD      drivers/i2c/built-in.o
  CC      drivers/interrupt_controller/system_apic.o
  CC      drivers/interrupt_controller/loapic_intr.o
  CC      drivers/interrupt_controller/ioapic_intr.o
  LD      drivers/interrupt_controller/built-in.o
  CC      drivers/pci/pci.o
  CC      drivers/pci/pci_config.o
  CC      drivers/pci/pci_interface.o
  CC      drivers/pci/pci_legacy_bridge.o
  LD      drivers/pci/built-in.o
  LD      drivers/pinmux/built-in.o
  CC      drivers/pwm/pwm_pca9685.o
  LD      drivers/pwm/built-in.o
  LD      drivers/random/built-in.o
  CC      drivers/serial/uart_ns16550.o
  LD      drivers/serial/built-in.o
  CC      drivers/shared_irq/shared_irq.o
  LD      drivers/shared_irq/built-in.o
  CC      drivers/spi/spi_intel.o
  LD      drivers/spi/built-in.o
  CC      drivers/timer/hpet.o
  CC      drivers/timer/sys_clock_init.o
  LD      drivers/timer/built-in.o
  LD      drivers/built-in.o
  CC      samples/hello_world/microkernel/src/main.o
  LD      samples/hello_world/microkernel/src/built-in.o
  LINK    zephyr.lnk
  SIDT    staticIdt.o
  LINK    zephyr.elf
  BIN     zephyr.bin
make[2]: Leaving directory `/home/abraham/zephyr-project/samples/hello_world/microkernel/outdir'
make[1]: Leaving directory `/home/abraham/zephyr-project'
user@workstation:~/zephyr-project/samples/hello_world/microkernel$
```

### Setting the Project’s Environment Variables

```bash
    user@workstation:~$ cd zephyr-project 
    user@workstation:~/zephyr-project$ source zephyr-env.sh
```

### Building a Sample Application, Default

```bash
    user@workstation:~$ cd $ZEPHYR_BASE/samples/hello_world/microkernel
    user@workstation:~/zephyr-project/samples/hello_world/microkernel$ make
    Using /home/xe1gyq/zephyr-project/boards/qemu_x86/qemu_x86_defconfig as base
    Merging /home/xe1gyq/zephyr-project/kernel/configs/micro.config
    Merging prj.conf
    #
    # configuration written to .config
    #
    make[1]: Entering directory '/home/xe1gyq/zephyr-project'
    make[2]: Entering directory '/home/xe1gyq/zephyr-project/samples/hello_world/microkernel/outdir'
      GEN     ./Makefile
    scripts/kconfig/conf --silentoldconfig Kconfig
      Using /home/xe1gyq/zephyr-project as source for kernel
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
      CC      kernel/microkernel/k_irq.o
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
      LD      kernel/nanokernel/built-in.o
      LD      kernel/built-in.o
      CC      misc/printk.o
      CC      misc/debug/mem_safe_check_boundaries.o
      LD      misc/debug/built-in.o
      CC      misc/generated/configs.o
      CC      misc/generated/sysgen/kernel_main.o
      LD      misc/generated/sysgen/built-in.o
      LD      misc/generated/built-in.o
      LD      misc/built-in.o
      LD      net/built-in.o
      CC      boards/qemu_x86/board.o
      LD      boards/qemu_x86/built-in.o
      LD      boards/built-in.o
      AS      arch/x86/core/i386_sysV_abi/intstub.o
      AS      arch/x86/core/i386_sysV_abi/swap.o
      CC      arch/x86/core/i386_sysV_abi/thread.o
      LD      arch/x86/core/i386_sysV_abi/built-in.o
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
      CC      arch/x86/core/strtask.o
      AS      arch/x86/core/errno.o
      LD      arch/x86/core/built-in.o
      CC      arch/x86/soc/ia32/soc.o
      LD      arch/x86/soc/ia32/built-in.o
      LD      arch/x86/built-in.o
      LD      arch/built-in.o
      LD      drivers/aio/built-in.o
      CC      drivers/console/uart_console.o
      LD      drivers/console/built-in.o
      CC      drivers/interrupt_controller/i8259.o
      CC      drivers/interrupt_controller/system_apic.o
      CC      drivers/interrupt_controller/loapic_intr.o
      CC      drivers/interrupt_controller/ioapic_intr.o
      LD      drivers/interrupt_controller/built-in.o
      LD      drivers/random/built-in.o
      CC      drivers/serial/uart_ns16550.o
      LD      drivers/serial/built-in.o
      CC      drivers/timer/hpet.o
      CC      drivers/timer/sys_clock_init.o
      LD      drivers/timer/built-in.o
      LD      drivers/built-in.o
      CC      samples/hello_world/microkernel/src/main.o
      LD      samples/hello_world/microkernel/src/built-in.o
      LINK    zephyr.lnk
      SIDT    staticIdt.o
      LINK    zephyr.elf
      BIN     zephyr.bin
    make[2]: Leaving directory '/home/xe1gyq/zephyr-project/samples/hello_world/microkernel/outdir'
    make[1]: Leaving directory '/home/xe1gyq/zephyr-project'
    user@workstation:~/zephyr-project/samples/hello_world/microkernel$ make distclean
    make[1]: Entering directory '/home/xe1gyq/zephyr-project'
    make[2]: Entering directory '/home/xe1gyq/zephyr-project/samples/hello_world/microkernel/outdir'
      CLEAN   .
      CLEAN   misc/generated/sysgen/kernel_main.c misc/generated/sysgen/sysgen.h misc/generated/sysgen/prj.mdef .tmp_zephyr.prebuilt zephyr.lnk zephyr.map zephyr.elf zephyr.lst zephyr.bin zephyr.strip staticIdt.o linker.cmd final-linker.cmd
      CLEAN   scripts/basic
      CLEAN   scripts/gen_idt
      CLEAN   scripts/kconfig
      CLEAN   include/config include/generated
      CLEAN   .config .config.old include/generated/version.h
    make[2]: Leaving directory '/home/xe1gyq/zephyr-project/samples/hello_world/microkernel/outdir'
    make[1]: Leaving directory '/home/xe1gyq/zephyr-project'
    user@workstation:~/zephyr-project/samples/hello_world/microkernel$
```

