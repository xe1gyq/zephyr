# Development Environment

## Development Environment

## Development Environment Setup on Linux

### Libraries Update

```bash
user@workstation:~$ sudo apt-get update
Get:1 http://security.ubuntu.com trusty-security InRelease [65.9 kB]
Get:2 http://packages.ros.org trusty InRelease [4 031 B]                       
Ign http://extras.ubuntu.com trusty InRelease                                  
Hit http://ppa.launchpad.net trusty InRelease                                  
Ign http://mx.archive.ubuntu.com trusty InRelease                              
Get:3 http://packages.ros.org trusty/main amd64 Packages [702 kB]              
Get:4 http://extras.ubuntu.com trusty Release.gpg [72 B]                       
Get:5 http://mx.archive.ubuntu.com trusty-updates InRelease [65.9 kB]          
Hit http://ppa.launchpad.net trusty/main amd64 Packages                        
Get:6 http://security.ubuntu.com trusty-security/main Sources [116 kB]         
Hit http://extras.ubuntu.com trusty Release                                    
Hit http://ppa.launchpad.net trusty/main i386 Packages                         
Get:7 http://security.ubuntu.com trusty-security/restricted Sources [4 035 B]  
Hit http://extras.ubuntu.com trusty/main Sources                               
Get:8 http://security.ubuntu.com trusty-security/universe Sources [37.3 kB]    
Hit http://ppa.launchpad.net trusty/main Translation-en                        
Get:9 http://security.ubuntu.com trusty-security/multiverse Sources [2 757 B]  
Hit http://extras.ubuntu.com trusty/main amd64 Packages                        
Hit http://mx.archive.ubuntu.com trusty-backports InRelease                    
Get:10 http://security.ubuntu.com trusty-security/main amd64 Packages [493 kB] 
Get:11 http://packages.ros.org trusty/main i386 Packages [702 kB]              
Hit http://extras.ubuntu.com trusty/main i386 Packages                         
Hit http://mx.archive.ubuntu.com trusty Release.gpg                            
Get:12 http://mx.archive.ubuntu.com trusty-updates/main Sources [277 kB]       
Get:13 http://security.ubuntu.com trusty-security/restricted amd64 Packages [13.0 kB]
Get:14 http://security.ubuntu.com trusty-security/universe amd64 Packages [130 kB]
Get:15 http://security.ubuntu.com trusty-security/multiverse amd64 Packages [4 989 B]
Get:16 http://security.ubuntu.com trusty-security/main i386 Packages [464 kB]  
Ign http://repos.tel.red stable InRelease                                      
Get:17 http://mx.archive.ubuntu.com trusty-updates/restricted Sources [5 352 B]
Get:18 http://security.ubuntu.com trusty-security/restricted i386 Packages [12.7 kB]
Get:19 http://security.ubuntu.com trusty-security/universe i386 Packages [130 kB]
Get:20 http://mx.archive.ubuntu.com trusty-updates/universe Sources [157 kB]   
Get:21 http://security.ubuntu.com trusty-security/multiverse i386 Packages [5 170 B]
Hit http://repos.tel.red stable Release.gpg                                    
Get:22 http://security.ubuntu.com trusty-security/main Translation-en [271 kB] 
Get:23 http://mx.archive.ubuntu.com trusty-updates/multiverse Sources [5 936 B]
Ign http://packages.ros.org trusty/main Translation-en_US                      
Get:24 http://security.ubuntu.com trusty-security/multiverse Translation-en [2 570 B]
Ign http://packages.ros.org trusty/main Translation-en                         
Get:25 http://mx.archive.ubuntu.com trusty-updates/main amd64 Packages [781 kB]
Get:26 http://security.ubuntu.com trusty-security/restricted Translation-en [3 206 B]
Get:27 http://security.ubuntu.com trusty-security/universe Translation-en [76.6 kB]
Hit http://repos.tel.red stable Release                                        
Ign http://extras.ubuntu.com trusty/main Translation-en_US                     
Ign http://extras.ubuntu.com trusty/main Translation-en                 
Get:28 http://mx.archive.ubuntu.com trusty-updates/restricted amd64 Packages [15.9 kB]
Get:29 http://mx.archive.ubuntu.com trusty-updates/universe amd64 Packages [362 kB]
Hit http://repos.tel.red stable/non-free amd64 Packages   
Hit http://repos.tel.red stable/non-free i386 Packages                      
Get:30 http://mx.archive.ubuntu.com trusty-updates/multiverse amd64 Packages [13.2 kB]
Get:31 http://mx.archive.ubuntu.com trusty-updates/main i386 Packages [748 kB]
Get:32 http://mx.archive.ubuntu.com trusty-updates/restricted i386 Packages [15.6 kB]
Get:33 http://mx.archive.ubuntu.com trusty-updates/universe i386 Packages [363 kB]
Get:34 http://mx.archive.ubuntu.com trusty-updates/multiverse i386 Packages [13.6 kB]
Get:35 http://mx.archive.ubuntu.com trusty-updates/main Translation-en [391 kB]
Get:36 http://mx.archive.ubuntu.com trusty-updates/multiverse Translation-en [7 227 B]
Get:37 http://mx.archive.ubuntu.com trusty-updates/restricted Translation-en [3 699 B]
Get:38 http://mx.archive.ubuntu.com trusty-updates/universe Translation-en [189 kB]
Ign http://repos.tel.red stable/non-free Translation-en_US                     
Ign http://repos.tel.red stable/non-free Translation-en                        
Hit http://mx.archive.ubuntu.com trusty-backports/main Sources                 
Hit http://mx.archive.ubuntu.com trusty-backports/restricted Sources           
Hit http://mx.archive.ubuntu.com trusty-backports/universe Sources             
Hit http://mx.archive.ubuntu.com trusty-backports/multiverse Sources           
Hit http://mx.archive.ubuntu.com trusty-backports/main amd64 Packages          
Hit http://mx.archive.ubuntu.com trusty-backports/restricted amd64 Packages    
Hit http://mx.archive.ubuntu.com trusty-backports/universe amd64 Packages      
Hit http://mx.archive.ubuntu.com trusty-backports/multiverse amd64 Packages    
Hit http://mx.archive.ubuntu.com trusty-backports/main i386 Packages           
Hit http://mx.archive.ubuntu.com trusty-backports/restricted i386 Packages     
Hit http://mx.archive.ubuntu.com trusty-backports/universe i386 Packages       
Hit http://mx.archive.ubuntu.com trusty-backports/multiverse i386 Packages     
Hit http://mx.archive.ubuntu.com trusty-backports/main Translation-en          
Hit http://mx.archive.ubuntu.com trusty-backports/multiverse Translation-en    
Hit http://mx.archive.ubuntu.com trusty-backports/restricted Translation-en    
Hit http://mx.archive.ubuntu.com trusty-backports/universe Translation-en      
Hit http://mx.archive.ubuntu.com trusty Release                                
Hit http://mx.archive.ubuntu.com trusty/main Sources                           
Hit http://mx.archive.ubuntu.com trusty/restricted Sources                     
Hit http://mx.archive.ubuntu.com trusty/universe Sources                       
Hit http://mx.archive.ubuntu.com trusty/multiverse Sources                     
Hit http://mx.archive.ubuntu.com trusty/main amd64 Packages                    
Hit http://mx.archive.ubuntu.com trusty/restricted amd64 Packages              
Hit http://mx.archive.ubuntu.com trusty/universe amd64 Packages                
Hit http://mx.archive.ubuntu.com trusty/multiverse amd64 Packages              
Hit http://mx.archive.ubuntu.com trusty/main i386 Packages                     
Hit http://mx.archive.ubuntu.com trusty/restricted i386 Packages               
Hit http://mx.archive.ubuntu.com trusty/universe i386 Packages                 
Hit http://mx.archive.ubuntu.com trusty/multiverse i386 Packages               
Hit http://mx.archive.ubuntu.com trusty/main Translation-en                    
Hit http://mx.archive.ubuntu.com trusty/multiverse Translation-en              
Hit http://mx.archive.ubuntu.com trusty/restricted Translation-en              
Hit http://mx.archive.ubuntu.com trusty/universe Translation-en                
Ign http://mx.archive.ubuntu.com trusty/main Translation-en_US                 
Ign http://mx.archive.ubuntu.com trusty/multiverse Translation-en_US           
Ign http://mx.archive.ubuntu.com trusty/restricted Translation-en_US           
Ign http://mx.archive.ubuntu.com trusty/universe Translation-en_US             
Fetched 6 655 kB in 25s (264 kB/s)                                            
Reading package lists... Done
user@workstation:~$
```

```bash
xe1gyq@jessie:~# apt-get install git make gcc gcc-multilib g++ libc6-dev-i386 g++-multilib python3-ply
```

### Development Environment SDK

[Zephyr SDK Archive](https://nexus.zephyrproject.org/content/repositories/releases/org/zephyrproject/zephyr-sdk/)

```bash
user@workstation:~$ wget https://nexus.zephyrproject.org/content/repositories/releases/org/zephyrproject/zephyr-sdk/0.8-i686/zephyr-sdk-0.8-i686-setup.run
```

```bash
--2016-06-25 11:48:38-- https://nexus.zephyrproject.org/content/repositories/releases/org/zephyrproject/zephyr-sdk/0.8-i686/zephyr-sdk-0.8-i686-setup.run
Resolving nexus.zephyrproject.org (nexus.zephyrproject.org)... 199.19.213.246
Connecting to nexus.zephyrproject.org (nexus.zephyrproject.org)|199.19.213.246|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 378809314 (361M) [application/octet-stream]
Saving to: ‘zephyr-sdk-0.8-i686-setup.run’

100%[======================================>] 378 809 314 1.29MB/s   in 5m 42s 

2016-06-25 11:54:21 (1.06 MB/s) - ‘zephyr-sdk-0.8-i686-setup.run’ saved [378809314/378809314]
```

```bash
user@workstation:~$ chmod +x zephyr-sdk-0.8-i686-setup.run 
user@workstation:~$ sudo ./zephyr-sdk-<version>-i686-setup.run
[sudo] password for abraham:
```

```bash
Verifying archive integrity... All good.
Uncompressing SDK for Zephyr  100%  
Enter target directory for SDK (default: /opt/zephyr-sdk/): 
Installing SDK to /opt/zephyr-sdk
Creating directory /opt/zephyr-sdk
Success
 [*] Installing x86 tools... 
 [*] Installing arm tools... 
 [*] Installing arc tools... 
 [*] Installing iamcu tools... 
 [*] Installing mips tools... 
 [*] Installing nios2 tools... 
 [*] Installing additional host tools... 
Success installing SDK. SDK is ready to be used.
user@workstation:~$
```

```bash
user@workstation:~$ export ZEPHYR_GCC_VARIANT=zephyr
user@workstation:~$ export ZEPHYR_SDK_INSTALL_DIR=/opt/zephyr-sdk
user@workstation:~$
```

```bash
user@workstation:~$ cat << EOF > ~/.zephyrrc
export ZEPHYR_GCC_VARIANT=zephyr
export ZEPHYR_SDK_INSTALL_DIR=/opt/zephyr-sdk
EOF
```

