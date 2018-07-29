# Device Drivers GPIO

```bash
user@workstation:~/zephyr-project$ ls
arch    drivers  Kbuild          kernel   MAINTAINERS   misc     scripts
boards  ext      Kconfig         lib      Makefile      net      tests
doc     include  Kconfig.zephyr  LICENSE  Makefile.inc  samples  zephyr-env.sh
user@workstation:~/zephyr-project$ cd drivers/gpio/
user@workstation:~/zephyr-project/drivers/gpio$ ls
gpio_api_compat.c    gpio_mmio.c       gpio_sch.h          Kconfig.mmio
gpio_api_compat.h    gpio_mmio.h       gpio_stm32.c        Kconfig.nrf5
gpio_atmel_sam3.c    gpio_nrf5.c       gpio_stm32.h        Kconfig.pcal9535a
gpio_dw.c            gpio_pcal9535a.c  gpio_utils.h        Kconfig.qmsi
gpio_dw.h            gpio_pcal9535a.h  Kconfig             Kconfig.qmsi_ss
gpio_dw_registers.h  gpio_qmsi.c       Kconfig.atmel_sam3  Kconfig.sch
gpio_k64.c           gpio_qmsi_ss.c    Kconfig.dw          Kconfig.stm32
gpio_k64.h           gpio_sch.c        Kconfig.k64         Makefile
user@workstation:~/zephyr-project/drivers/gpio$
```

```bash
user@workstation:~/zephyr-project/drivers/gpio$ nano gpio_qmsi.c
```

```c
...

struct gpio_qmsi_config {
        qm_gpio_t gpio;
        uint8_t num_pins;
};

struct gpio_qmsi_runtime {
        sys_slist_t callbacks;
        uint32_t pin_callbacks;
};

...

int gpio_qmsi_init(struct device *dev);

...

static inline int gpio_qmsi_write(struct device *port,
                                  int access_op, uint32_t pin, uint32_t value)

...
```

