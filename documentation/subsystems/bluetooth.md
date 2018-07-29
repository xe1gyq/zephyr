# Bluetooth

## Bluetooth

```bash
user@workstation:~/zephyr-project/samples/bluetooth$ cat README
```

### At Linux Host

```bash
user@workstation:~$ sudo apt-get install bluez bluez-utils bluez-tools libbluetooth-dev python-dev
Reading package lists... Done
Building dependency tree       
Reading state information... Done
python-dev is already the newest version.
bluez-tools is already the newest version.
bluez is already the newest version.
libbluetooth-dev is already the newest version.
bluez-utils is already the newest version.
0 upgraded, 0 newly installed, 0 to remove and 393 not upgraded.
user@workstation:~$
```

### Not the right btproxy

```bash
user@workstation:~$ git clone https://github.com/conorpp/btproxy
Cloning into 'btproxy'...
remote: Counting objects: 310, done.
remote: Total 310 (delta 0), reused 0 (delta 0), pack-reused 310
Receiving objects: 100% (310/310), 120.06 KiB | 0 bytes/s, done.
Resolving deltas: 100% (186/186), done.
Checking connectivity... done.
```

```bash
user@workstation:~$ cd btproxy/
user@workstation:~/btproxy$ sudo python setup.py install
...
Adding PyBluez 0.22 to easy-install.pth file

Installed /usr/local/lib/python2.7/dist-packages/PyBluez-0.22-py2.7-linux-x86_64.egg
Finished processing dependencies for btproxy==0.1
user@workstation:~/btproxy$
```

### BlueZ

```bash
user@workstation:~$ sudo apt-get install libical-dev
```

```bash
user@workstation:~$ git clone https://git.kernel.org/pub/scm/bluetooth/bluez.git
user@workstation:~$ cd bluez
```

```bash
user@workstation:~/bluez$ ./configure --prefix=/usr --mandir=/usr/share/man --sysconfdir=/etc --localstatedir=/var --enable-experimental --with-systemdsystemunitdir=/lib/systemd/system --with-systemduserunitdir=/usr/lib/systemd
user@workstation:~/bluez$ make
...
```

## Host, Before

```bash
user@workstation:~/bluez$ sudo hciconfig 
hci0:    Type: BR/EDR  Bus: USB
    BD Address: E8:B1:FC:09:6A:FE  ACL MTU: 1021:5  SCO MTU: 96:5
    UP RUNNING PSCAN ISCAN 
    RX bytes:2780 acl:0 sco:0 events:207 errors:0
    TX bytes:22720 acl:0 sco:0 commands:181 errors:0
```

```bash
user@workstation:~/bluez$ sudo hciconfig hci0 down
```

```bash
user@workstation:~/bluez$ sudo hciconfig 
hci0:    Type: BR/EDR  Bus: USB
    BD Address: E8:B1:FC:09:6A:FE  ACL MTU: 1021:5  SCO MTU: 96:5
    DOWN 
    RX bytes:2780 acl:0 sco:0 events:207 errors:0
    TX bytes:22720 acl:0 sco:0 commands:181 errors:0
```

```bash
user@workstation:~/bluez$ sudo tools/btproxy -u
Listening on /tmp/bt-server-bredr
```

### Bluetooth Samples

```bash
user@workstation:~/zephyr-project$ ls
arch    drivers  Kbuild          kernel   MAINTAINERS   misc     scripts
boards  ext      Kconfig         lib      Makefile      net      tests
doc     include  Kconfig.zephyr  LICENSE  Makefile.inc  samples  zephyr-env.sh
user@workstation:~/zephyr-project$ cd samples/bluetooth/
user@workstation:~/zephyr-project/samples/bluetooth$ ls
beacon   central_hr  ipsp        peripheral_csc  peripheral_esp  peripheral_sc_only
central  gatt        peripheral  peripheral_dis  peripheral_hr   README
user@workstation:~/zephyr-project/samples/bluetooth$
```

```bash
user@workstation:~/zephyr-project/samples/bluetooth$ cd peripheral_hr/
user@workstation:~/zephyr-project/samples/bluetooth/peripheral_hr$ ls
Makefile  prj.conf  prj.mdef  prj_nble.conf  README  src  testcase.ini
user@workstation:~/zephyr-project/samples/bluetooth/peripheral_hr$ make pristine && make qemu
...
To exit from QEMU enter: 'CTRL+a, x'
[QEMU] CPU: qemu32
Bluetooth initialized
Advertising successfully started
```

### Host, After

```bash
user@workstation:~/bluez$ sudo tools/btproxy -u
Listening on /tmp/bt-server-bredr
Opening user channel for hci0
New client connected
```

