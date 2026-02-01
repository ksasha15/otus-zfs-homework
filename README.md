# otus-zfs-homework

root@u24:~# apt install zfsutils-linux
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libnvpair3linux libuutil3linux libzfs4linux libzpool5linux zfs-zed
Suggested packages:
  nfs-kernel-server samba-common-bin zfs-initramfs | zfs-dracut
The following NEW packages will be installed:
  libnvpair3linux libuutil3linux libzfs4linux libzpool5linux zfs-zed
  zfsutils-linux
0 upgraded, 6 newly installed, 0 to remove and 60 not upgraded.
Need to get 2,355 kB of archives.
After this operation, 7,399 kB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://ru.archive.ubuntu.com/ubuntu noble-updates/main amd64 libnvpair3linux amd64 2.2.2-0ubuntu9.4 [62.1 kB]
Get:2 http://ru.archive.ubuntu.com/ubuntu noble-updates/main amd64 libuutil3linux amd64 2.2.2-0ubuntu9.4 [53.2 kB]
Get:3 http://ru.archive.ubuntu.com/ubuntu noble-updates/main amd64 libzfs4linux amd64 2.2.2-0ubuntu9.4 [224 kB]
Get:4 http://ru.archive.ubuntu.com/ubuntu noble-updates/main amd64 libzpool5linux amd64 2.2.2-0ubuntu9.4 [1,397 kB]
Get:5 http://ru.archive.ubuntu.com/ubuntu noble-updates/main amd64 zfsutils-linux amd64 2.2.2-0ubuntu9.4 [551 kB]
Get:6 http://ru.archive.ubuntu.com/ubuntu noble-updates/main amd64 zfs-zed amd64 2.2.2-0ubuntu9.4 [67.9 kB]
Fetched 2,355 kB in 3s (814 kB/s)
Selecting previously unselected package libnvpair3linux.
(Reading database ... 87472 files and directories currently installed.)
Preparing to unpack .../0-libnvpair3linux_2.2.2-0ubuntu9.4_amd64.deb ...
Unpacking libnvpair3linux (2.2.2-0ubuntu9.4) ...
Selecting previously unselected package libuutil3linux.
Preparing to unpack .../1-libuutil3linux_2.2.2-0ubuntu9.4_amd64.deb ...
Unpacking libuutil3linux (2.2.2-0ubuntu9.4) ...
Selecting previously unselected package libzfs4linux.
Preparing to unpack .../2-libzfs4linux_2.2.2-0ubuntu9.4_amd64.deb ...
Unpacking libzfs4linux (2.2.2-0ubuntu9.4) ...
Selecting previously unselected package libzpool5linux.
Preparing to unpack .../3-libzpool5linux_2.2.2-0ubuntu9.4_amd64.deb ...
Unpacking libzpool5linux (2.2.2-0ubuntu9.4) ...
Selecting previously unselected package zfsutils-linux.
Preparing to unpack .../4-zfsutils-linux_2.2.2-0ubuntu9.4_amd64.deb ...
Unpacking zfsutils-linux (2.2.2-0ubuntu9.4) ...
Selecting previously unselected package zfs-zed.
Preparing to unpack .../5-zfs-zed_2.2.2-0ubuntu9.4_amd64.deb ...
Unpacking zfs-zed (2.2.2-0ubuntu9.4) ...
Setting up libnvpair3linux (2.2.2-0ubuntu9.4) ...
Setting up libuutil3linux (2.2.2-0ubuntu9.4) ...
Setting up libzpool5linux (2.2.2-0ubuntu9.4) ...
Setting up libzfs4linux (2.2.2-0ubuntu9.4) ...
Setting up zfsutils-linux (2.2.2-0ubuntu9.4) ...
insmod /lib/modules/6.8.0-90-generic/kernel/zfs/spl.ko.zst
insmod /lib/modules/6.8.0-90-generic/kernel/zfs/zfs.ko.zst
Created symlink /etc/systemd/system/zfs-import.target.wants/zfs-import-cache.service → /usr/lib/systemd/system/zfs-import-cache.service.
Created symlink /etc/systemd/system/zfs.target.wants/zfs-import.target → /usr/lib/systemd/system/zfs-import.target.
Created symlink /etc/systemd/system/zfs-mount.service.wants/zfs-load-module.service → /usr/lib/systemd/system/zfs-load-module.service.
Created symlink /etc/systemd/system/zfs.target.wants/zfs-load-module.service → /usr/lib/systemd/system/zfs-load-module.service.
Created symlink /etc/systemd/system/zfs.target.wants/zfs-mount.service → /usr/lib/systemd/system/zfs-mount.service.
Created symlink /etc/systemd/system/zfs.target.wants/zfs-share.service → /usr/lib/systemd/system/zfs-share.service.
Created symlink /etc/systemd/system/zfs-volumes.target.wants/zfs-volume-wait.service → /usr/lib/systemd/system/zfs-volume-wait.service.
Created symlink /etc/systemd/system/zfs.target.wants/zfs-volumes.target → /usr/lib/systemd/system/zfs-volumes.target.
Created symlink /etc/systemd/system/multi-user.target.wants/zfs.target → /usr/lib/systemd/system/zfs.target.
zfs-import-scan.service is a disabled or a static unit, not starting it.
Setting up zfs-zed (2.2.2-0ubuntu9.4) ...
Created symlink /etc/systemd/system/zed.service → /usr/lib/systemd/system/zfs-zed.service.
Created symlink /etc/systemd/system/zfs.target.wants/zfs-zed.service → /usr/lib/systemd/system/zfs-zed.service.
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for libc-bin (2.39-0ubuntu8.6) ...
Scanning processes...
Scanning linux images...

Running kernel seems to be up-to-date.

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
root@u24:~#
root@u24:~# zpool create otus1 mirror /dev/sdb /dev/sdc
root@u24:~# zpool create otus2 mirror /dev/sdd /dev/sde
root@u24:~# zpool create otus3 mirror /dev/sdf /dev/sdg
root@u24:~# zpool create otus4 mirror /dev/sdh /dev/sdi
root@u24:~# zpool list
NAME    SIZE  ALLOC   FREE  CKPOINT  EXPANDSZ   FRAG    CAP  DEDUP    HEALTH  ALTROOT
otus1   480M   110K   480M        -         -     0%     0%  1.00x    ONLINE  -
otus2   480M   110K   480M        -         -     0%     0%  1.00x    ONLINE  -
otus3   480M   110K   480M        -         -     0%     0%  1.00x    ONLINE  -
otus4   480M   110K   480M        -         -     0%     0%  1.00x    ONLINE  -
root@u24:~# zpool status
  pool: otus1
 state: ONLINE
config:

        NAME        STATE     READ WRITE CKSUM
        otus1       ONLINE       0     0     0
          mirror-0  ONLINE       0     0     0
            sdb     ONLINE       0     0     0
            sdc     ONLINE       0     0     0

errors: No known data errors

  pool: otus2
 state: ONLINE
config:

        NAME        STATE     READ WRITE CKSUM
        otus2       ONLINE       0     0     0
          mirror-0  ONLINE       0     0     0
            sdd     ONLINE       0     0     0
            sde     ONLINE       0     0     0

errors: No known data errors

  pool: otus3
 state: ONLINE
config:

        NAME        STATE     READ WRITE CKSUM
        otus3       ONLINE       0     0     0
          mirror-0  ONLINE       0     0     0
            sdf     ONLINE       0     0     0
            sdg     ONLINE       0     0     0

errors: No known data errors

  pool: otus4
 state: ONLINE
config:

        NAME        STATE     READ WRITE CKSUM
        otus4       ONLINE       0     0     0
          mirror-0  ONLINE       0     0     0
            sdh     ONLINE       0     0     0
            sdi     ONLINE       0     0     0

errors: No known data errors
root@u24:~#
root@u24:~# zfs set compression=lzjb otus1
root@u24:~# zfs set compression=lz4 otus2
root@u24:~# zfs set compression=gzip-9 otus3
root@u24:~# zfs set compression=zle otus4
root@u24:~# zfs get all | grep compression
otus1  compression           lzjb                   local
otus2  compression           lz4                    local
otus3  compression           gzip-9                 local
otus4  compression           zle                    local
root@u24:~#
root@u24:~# for i in {1..4}; do wget -P /otus$i https://gutenberg.org/cache/epub/2600/pg2600.converter.log; done
--2026-02-01 02:13:18--  https://gutenberg.org/cache/epub/2600/pg2600.converter.log
Resolving gutenberg.org (gutenberg.org)... 152.19.134.47, 2610:28:3090:3000:0:bad:cafe:47
Connecting to gutenberg.org (gutenberg.org)|152.19.134.47|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 41204725 (39M) [text/plain]
Saving to: ‘/otus1/pg2600.converter.log’

pg2600.converter.log 100%[===================>]  39.29M  1.88MB/s    in 21s

2026-02-01 02:13:41 (1.90 MB/s) - ‘/otus1/pg2600.converter.log’ saved [41204725/41204725]

--2026-02-01 02:13:41--  https://gutenberg.org/cache/epub/2600/pg2600.converter.log
Resolving gutenberg.org (gutenberg.org)... 152.19.134.47, 2610:28:3090:3000:0:bad:cafe:47
Connecting to gutenberg.org (gutenberg.org)|152.19.134.47|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 41204725 (39M) [text/plain]
Saving to: ‘/otus2/pg2600.converter.log’

pg2600.converter.log  90%[=================>  ]  35.54M  52.5KB/s    in 6m 9s

2026-02-01 02:19:52 (98.5 KB/s) - Connection closed at byte 37264659. Retrying.

--2026-02-01 02:19:53--  (try: 2)  https://gutenberg.org/cache/epub/2600/pg2600.converter.log
Connecting to gutenberg.org (gutenberg.org)|152.19.134.47|:443... connected.
HTTP request sent, awaiting response... 206 Partial Content
Length: 41204725 (39M), 3940066 (3.8M) remaining [text/plain]
Saving to: ‘/otus2/pg2600.converter.log’

pg2600.converter.log 100%[++++++++++++++++++=>]  39.29M   987KB/s    in 3.9s

2026-02-01 02:19:58 (987 KB/s) - ‘/otus2/pg2600.converter.log’ saved [41204725/41204725]

--2026-02-01 02:19:58--  https://gutenberg.org/cache/epub/2600/pg2600.converter.log
Resolving gutenberg.org (gutenberg.org)... 152.19.134.47, 2610:28:3090:3000:0:bad:cafe:47
Connecting to gutenberg.org (gutenberg.org)|152.19.134.47|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 41204725 (39M) [text/plain]
Saving to: ‘/otus3/pg2600.converter.log’

pg2600.converter.log  91%[=================>  ]  35.96M  98.7KB/s    in 5m 35s

2026-02-01 02:25:35 (110 KB/s) - Connection closed at byte 37707943. Retrying.

--2026-02-01 02:25:36--  (try: 2)  https://gutenberg.org/cache/epub/2600/pg2600.converter.log
Connecting to gutenberg.org (gutenberg.org)|152.19.134.47|:443... connected.
HTTP request sent, awaiting response... 206 Partial Content
Length: 41204725 (39M), 3496782 (3.3M) remaining [text/plain]
Saving to: ‘/otus3/pg2600.converter.log’

pg2600.converter.log 100%[++++++++++++++++++=>]  39.29M   115KB/s    in 23s

2026-02-01 02:26:00 (151 KB/s) - ‘/otus3/pg2600.converter.log’ saved [41204725/41204725]

--2026-02-01 02:26:00--  https://gutenberg.org/cache/epub/2600/pg2600.converter.log
Resolving gutenberg.org (gutenberg.org)... 152.19.134.47, 2610:28:3090:3000:0:bad:cafe:47
Connecting to gutenberg.org (gutenberg.org)|152.19.134.47|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 41204725 (39M) [text/plain]
Saving to: ‘/otus4/pg2600.converter.log’

pg2600.converter.log  25%[====>               ]   9.91M  70.1KB/s    in 1m 52s

2026-02-01 02:27:53 (90.5 KB/s) - Connection closed at byte 10389691. Retrying.

--2026-02-01 02:27:54--  (try: 2)  https://gutenberg.org/cache/epub/2600/pg2600.converter.log
Connecting to gutenberg.org (gutenberg.org)|152.19.134.47|:443... connected.
HTTP request sent, awaiting response... 206 Partial Content
Length: 41204725 (39M), 30815034 (29M) remaining [text/plain]
Saving to: ‘/otus4/pg2600.converter.log’

pg2600.converter.log 100%[+++++==============>]  39.29M   138KB/s    in 4m 55s

2026-02-01 02:32:51 (102 KB/s) - ‘/otus4/pg2600.converter.log’ saved [41204725/41204725]

root@u24:~#
root@u24:~# ls -l /otus*
/otus1:
total 22118
-rw-r--r-- 1 root root 41204725 Jan  2 08:31 pg2600.converter.log

/otus2:
total 18018
-rw-r--r-- 1 root root 41204725 Jan  2 08:31 pg2600.converter.log

/otus3:
total 10973
-rw-r--r-- 1 root root 41204725 Jan  2 08:31 pg2600.converter.log

/otus4:
total 40270
-rw-r--r-- 1 root root 41204725 Jan  2 08:31 pg2600.converter.log
root@u24:~#
root@u24:~# zfs list
NAME    USED  AVAIL  REFER  MOUNTPOINT
otus1  21.7M   330M  21.6M  /otus1
otus2  17.8M   334M  17.6M  /otus2
otus3  10.9M   341M  10.7M  /otus3
otus4  39.5M   312M  39.3M  /otus4
root@u24:~# zfs get all | grep compressratio | grep -v ref
otus1  compressratio         1.82x                  -
otus2  compressratio         2.23x                  -
otus3  compressratio         3.66x                  -
otus4  compressratio         1.00x                  -
root@u24:~#
root@u24:~# wget -O archive.tar.gz --no-check-certificate 'https://drive.usercontent.google.com/download?id=1MvrcEp-WgAQe57aDEzxSRalPAwbNN1Bb&export=download'
--2026-02-01 02:47:35--  https://drive.usercontent.google.com/download?id=1MvrcEp-WgAQe57aDEzxSRalPAwbNN1Bb&export=download
Resolving drive.usercontent.google.com (drive.usercontent.google.com)... 173.194.221.132, 2a00:1450:4010:c0a::84
Connecting to drive.usercontent.google.com (drive.usercontent.google.com)|173.194.221.132|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 7275140 (6.9M) [application/octet-stream]
Saving to: ‘archive.tar.gz’

archive.tar.gz       100%[===================>]   6.94M  2.17MB/s    in 3.2s

2026-02-01 02:47:45 (2.17 MB/s) - ‘archive.tar.gz’ saved [7275140/7275140]

root@u24:~# ll
total 7148
drwx------  4 root root    4096 Feb  1 02:47 ./
drwxr-xr-x 28 root root    4096 Feb  1 01:31 ../
-rw-r--r--  1 root root    3979 Feb  1 01:50 1
-rw-r--r--  1 root root       0 Feb  1 01:42 2
-rw-r--r--  1 root root 7275140 Dec  6  2023 archive.tar.gz
-rw-------  1 root root    1467 Jan 28 16:43 .bash_history
-rw-r--r--  1 root root    3106 Apr 22  2024 .bashrc
drwx------  3 root root    4096 Jan 28 16:16 .config/
-rw-------  1 root root      80 Feb  1 02:46 .lesshst
-rw-r--r--  1 root root     161 Apr 22  2024 .profile
drwx------  2 root root    4096 Jan 25 14:52 .ssh/
-rw-------  1 root root    2056 Jan 28 16:42 .viminfo
root@u24:~#
root@u24:~# tar -xzvf archive.tar.gz
zpoolexport/
zpoolexport/filea
zpoolexport/fileb
root@u24:~# 
root@u24:~# zpool import -d zpoolexport/
   pool: otus
     id: 6554193320433390805
  state: ONLINE
status: Some supported features are not enabled on the pool.
        (Note that they may be intentionally disabled if the
        'compatibility' property is set.)
 action: The pool can be imported using its name or numeric identifier, though
        some features will not be available without an explicit 'zpool upgrade'.
 config:

        otus                         ONLINE
          mirror-0                   ONLINE
            /root/zpoolexport/filea  ONLINE
            /root/zpoolexport/fileb  ONLINE
root@u24:~#
root@u24:~#
root@u24:~# zpool import -d zpoolexport/ otus
root@u24:~# zpool status
  pool: otus
 state: ONLINE
status: Some supported and requested features are not enabled on the pool.
        The pool can still be used, but some features are unavailable.
action: Enable all features using 'zpool upgrade'. Once this is done,
        the pool may no longer be accessible by software that does not support
        the features. See zpool-features(7) for details.
config:

        NAME                         STATE     READ WRITE CKSUM
        otus                         ONLINE       0     0     0
          mirror-0                   ONLINE       0     0     0
            /root/zpoolexport/filea  ONLINE       0     0     0
            /root/zpoolexport/fileb  ONLINE       0     0     0

errors: No known data errors
root@u24:~# zfs get all otus
NAME  PROPERTY              VALUE                  SOURCE
otus  type                  filesystem             -
otus  creation              Fri May 15  4:00 2020  -
otus  used                  2.04M                  -
otus  available             350M                   -
otus  referenced            24K                    -
otus  compressratio         1.00x                  -
otus  mounted               yes                    -
otus  quota                 none                   default
otus  reservation           none                   default
otus  recordsize            128K                   local
otus  mountpoint            /otus                  default
otus  sharenfs              off                    default
otus  checksum              sha256                 local
otus  compression           zle                    local
otus  atime                 on                     default
otus  devices               on                     default
otus  exec                  on                     default
otus  setuid                on                     default
otus  readonly              off                    default
otus  zoned                 off                    default
otus  snapdir               hidden                 default
otus  aclmode               discard                default
otus  aclinherit            restricted             default
otus  createtxg             1                      -
otus  canmount              on                     default
otus  xattr                 on                     default
otus  copies                1                      default
otus  version               5                      -
otus  utf8only              off                    -
otus  normalization         none                   -
otus  casesensitivity       sensitive              -
otus  vscan                 off                    default
otus  nbmand                off                    default
otus  sharesmb              off                    default
otus  refquota              none                   default
otus  refreservation        none                   default
otus  guid                  14592242904030363272   -
otus  primarycache          all                    default
otus  secondarycache        all                    default
otus  usedbysnapshots       0B                     -
otus  usedbydataset         24K                    -
otus  usedbychildren        2.01M                  -
otus  usedbyrefreservation  0B                     -
otus  logbias               latency                default
otus  objsetid              54                     -
otus  dedup                 off                    default
otus  mlslabel              none                   default
otus  sync                  standard               default
otus  dnodesize             legacy                 default
otus  refcompressratio      1.00x                  -
otus  written               24K                    -
otus  logicalused           1020K                  -
otus  logicalreferenced     12K                    -
otus  volmode               default                default
otus  filesystem_limit      none                   default
otus  snapshot_limit        none                   default
otus  filesystem_count      none                   default
otus  snapshot_count        none                   default
otus  snapdev               hidden                 default
otus  acltype               off                    default
otus  context               none                   default
otus  fscontext             none                   default
otus  defcontext            none                   default
otus  rootcontext           none                   default
otus  relatime              on                     default
otus  redundant_metadata    all                    default
otus  overlay               on                     default
otus  encryption            off                    default
otus  keylocation           none                   default
otus  keyformat             none                   default
otus  pbkdf2iters           0                      default
otus  special_small_blocks  0                      default
root@u24:~# zfs get available otus
root@u24:~#
NAME  PROPERTY   VALUE  SOURCE
otus  available  350M   -
root@u24:~# zfs get readonly otus
NAME  PROPERTY  VALUE   SOURCE
otus  readonly  off     default
root@u24:~# zfs get recordsize otus
NAME  PROPERTY    VALUE    SOURCE
otus  recordsize  128K     local
root@u24:~# zfs get compression otus
NAME  PROPERTY     VALUE           SOURCE
otus  compression  zle             local
root@u24:~# zfs get checksum otus
NAME  PROPERTY  VALUE      SOURCE
otus  checksum  sha256     local
root@u24:~#
