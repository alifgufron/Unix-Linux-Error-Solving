#Problem

```
rsync -avhe src-folder/ dst-folder/
ld-elf.so.1: /usr/local/bin/rsync: Undefined symbol "locale_charset"
ld-elf.so.1: /usr/local/bin/rsync: Undefined symbol "locale_charset"
```
#Rsync Info
```
rsync-3.2.5
Name           : rsync
Version        : 3.2.5
Installed on   : Mon Oct 24 10:50:26 2022 WIB
Origin         : net/rsync
Architecture   : FreeBSD:12:i386
Prefix         : /usr/local
Categories     : net
Licenses       : GPLv3+
Maintainer     : rodrigo@FreeBSD.org
WWW            : http://rsync.samba.org/
Comment        : Network file distribution/synchronization utility
Options        :
        DOCS           : on
        FLAGS          : on
        ICONV          : on
        POPT_PORT      : off
        RENAMED        : off
        SSH            : on
        ZLIB_BASE      : on
Shared Libs required:
        libzstd.so.1
        libxxhash.so.0
        liblz4.so.1
        libiconv.so.2
Annotations    :
        FreeBSD_version: 1203000
        cpe            : cpe:2.3:a:samba:rsync:3.2.5:::::freebsd12:x86
        repo_type      : binary
        repository     : FreeBSD
Flat size      : 772KiB

```

#Solving

```
pkg install -f libiconv

Installed packages to be UPGRADED:
        libiconv: 1.14_11 -> 1.17
```

#Test Rsync
```
rsync -avh src-folder/ dst-folder/
sending incremental file list
./
file1.txt
file10.txt
file11.txt
file12.txt
file13.txt
file14.txt
file15.txt
file16.txt
file17.txt
file18.txt
file19.txt
file2.txt
file20.txt
file3.txt
file4.txt
file5.txt
file6.txt
file7.txt
file8.txt
file9.txt

sent 1.19K bytes  received 399 bytes  3.17K bytes/sec
total size is 0  speedup is 0.00
```
