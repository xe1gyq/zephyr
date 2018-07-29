# DFU

> Device Firmware Upgrade

* [DFU Util Github](https://github.com/Stefan-Schmidt/dfu-util) 

```bash
user@workstation:~$ git clone git://git.code.sf.net/p/dfu-util/dfu-util
Cloning into 'dfu-util'...
remote: Counting objects: 1825, done.
remote: Compressing objects: 100% (611/611), done.
remote: Total 1825 (delta 1302), reused 1672 (delta 1207)
Receiving objects: 100% (1825/1825), 371.87 KiB | 64.00 KiB/s, done.
Resolving deltas: 100% (1302/1302), done.
Checking connectivity... done.
user@workstation:~$ 

```sh
user@workstation:~$ cd dfu-util/
user@workstation:~/dfu-util$ ls
AUTHORS     ChangeLog     COPYING      DEVICES.txt    doc      Makefile.am  README  TODO
autogen.sh  configure.ac  device-logs  dfuse-pack.py  INSTALL  msvc         src     www
user@workstation:~/dfu-util$
```

```bash
user@workstation:~/dfu-util$ ./autogen.sh 
autoreconf: Entering directory `.'
autoreconf: configure.ac: not using Gettext
autoreconf: running: aclocal 
autoreconf: configure.ac: tracing
autoreconf: configure.ac: creating directory m4
autoreconf: configure.ac: not using Libtool
autoreconf: running: /usr/bin/autoconf
autoreconf: running: /usr/bin/autoheader
autoreconf: running: automake --add-missing --copy --no-force
configure.ac:16: installing 'm4/compile'
configure.ac:7: installing 'm4/install-sh'
configure.ac:7: installing 'm4/missing'
src/Makefile.am: installing 'm4/depcomp'
autoreconf: Leaving directory `.'
user@workstation:~/dfu-util$
```

```bash
user@workstation:~/dfu-util$ ls
aclocal.m4      ChangeLog    configure.ac  DEVICES.txt  Makefile.am  src
autogen.sh      config.h.in  COPYING       doc          Makefile.in  TODO
autom4te.cache  configure    device-logs   m4           README       www
user@workstation:~/dfu-util$ ./configure 
user@workstation:~/dfu-util$ make
user@workstation:~/dfu-util$ sudo make install
```

```bash
user@workstation:~/dfu-util$ dfu-util -V
dfu-util 0.9

Copyright 2005-2009 Weston Schmidt, Harald Welte and OpenMoko Inc.
Copyright 2010-2016 Tormod Volden and Stefan Schmidt
This program is Free Software and has ABSOLUTELY NO WARRANTY
Please report bugs to http://sourceforge.net/p/dfu-util/tickets/

user@workstation:~/dfu-util$
```

