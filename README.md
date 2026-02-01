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
