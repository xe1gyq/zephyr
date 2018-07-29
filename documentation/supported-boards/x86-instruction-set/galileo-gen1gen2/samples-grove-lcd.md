# Samples Grove LCD

```bash
user@workstation:~/zephyr-project$ cd $ZEPHYR_BASE/samples/drivers/grove_lcd
user@workstation:~/zephyr-project/samples/drivers/grove_lcd$ make distclean
user@workstation:~/zephyr-project/samples/drivers/grove_lcd$ make BOARD=galileo
user@workstation:~/zephyr-project/samples/drivers/grove_lcd# mount -t vfat /dev/sdb1 /media/sdcard/
user@workstation:~/zephyr-project/samples/drivers/grove_lcd# cp $ZEPHYR_BASE/samples/drivers/grove_lcd/outdir/zephyr.strip /media/sdcard/kernel/
user@workstation:~/zephyr-project/samples/drivers/grove_lcd$ umount /media/sdcard/
user@workstation:~/zephyr-project/samples/drivers/grove_lcd$
```

Booting the Galileo Board ... LCD Working?

