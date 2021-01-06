# Volume Group


https://www.digitalocean.com/community/tutorials/how-to-use-lvm-to-manage-storage-devices-on-ubuntu-16-04

https://www.digitalocean.com/community/tutorials/an-introduction-to-lvm-concepts-terminology-and-operations


## :a: Displaying (Human Readable) PV, VG, LV

### :round_pushpin: Physical Volume

```
$ sudo pvdisplay
  --- Physical volume ---
  PV Name               /dev/sda3
  VG Name               ubuntu-vg
  PV Size               <272.40 GiB / not usable 0   
  Allocatable           yes 
  PE Size               4.00 MiB
  Total PE              69734
  Free PE               34867
  Allocated PE          34867
  PV UUID               PEFNgZ-yJVF-RMSj-fbhw-beAv-ZOQ2-Hfo8ui
```


### :round_pushpin: Volume Group

```
$ sudo vgdisplay
  --- Volume group ---
  VG Name               ubuntu-vg
  System ID             
  Format                lvm2
  Metadata Areas        1
  Metadata Sequence No  2
  VG Access             read/write
  VG Status             resizable
  MAX LV                0
  Cur LV                1
  Open LV               1
  Max PV                0
  Cur PV                1
  Act PV                1
  VG Size               <272.40 GiB
  PE Size               4.00 MiB
  Total PE              69734
  Alloc PE / Size       34867 / <136.20 GiB
  Free  PE / Size       34867 / <136.20 GiB
  VG UUID               8sb1LI-88DD-xtxe-0HcR-9RzL-v7LF-Ns6pLg
```

### :round_pushpin: Logical Volume

```
$ sudo lvdisplay
  --- Logical volume ---
  LV Path                /dev/ubuntu-vg/ubuntu-lv
  LV Name                ubuntu-lv
  VG Name                ubuntu-vg
  LV UUID                JlDYcN-hq2d-VqFp-mbhc-YN5r-Mtjv-SpQMMH
  LV Write Access        read/write
  LV Creation host, time ubuntu-server, 2020-10-29 23:43:59 +0000
  LV Status              available
  # open                 1
  LV Size                <136.20 GiB
  Current LE             34867
  Segments               1
  Allocation             inherit
  Read ahead sectors     auto
  - currently set to     256
  Block device           253:0
```

## :b: Scripting PV, VG, LV

`??s` command is highly configurable and can display information in many different formats. It is frequently used in when scripting or automation is needed.

### :round_pushpin: Physical Volume

```
$ sudo pvs
  PV         VG        Fmt  Attr PSize    PFree   
  /dev/sda3  ubuntu-vg lvm2 a--  <272.40g <136.20g
```


### :round_pushpin: Volume Group

```
$ sudo vgs
  VG        #PV #LV #SN Attr   VSize    VFree   
  ubuntu-vg   1   1   0 wz--n- <272.40g <136.20g
```

### :round_pushpin: Logical Volume

```
$ sudo lvs
  LV        VG        Attr       LSize    Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  ubuntu-lv ubuntu-vg -wi-ao---- <136.20g 
```

## :ab: Scanning PV, VG, LV

`??scan` option scans the system and outputs `minimal` information about the `volumes` it finds

### :round_pushpin: Physical Volume

```
$ sudo pvscan
  PV /dev/sda3   VG ubuntu-vg       lvm2 [<272.40 GiB / <136.20 GiB free]
  Total: 1 [<272.40 GiB] / in use: 1 [<272.40 GiB] / in no VG: 0 [0   ]
```

### :round_pushpin: Volume Group

```
$ sudo vgscan
  Found volume group "ubuntu-vg" using metadata type lvm2
```

### :round_pushpin: Logical Volume

```
$ sudo lvmdiskscan
  /dev/loop0  [     <31.09 MiB] 
  /dev/loop2  [     <97.86 MiB] 
  /dev/sda2   [       1.00 GiB] 
  /dev/loop3  [      55.36 MiB] 
  /dev/sda3   [    <272.40 GiB] LVM physical volume
  /dev/loop4  [      70.56 MiB] 
  /dev/loop5  [      67.75 MiB] 
  /dev/loop6  [     219.18 MiB] 
  /dev/loop7  [    <219.20 MiB] 
  /dev/loop9  [      31.06 MiB] 
  /dev/loop10 [      55.38 MiB] 
  /dev/loop11 [      97.88 MiB] 
  0 disks
  11 partitions
  0 LVM physical volume whole disks
  1 LVM physical volume
```

## :o: Main

### :round_pushpin: LVM CLI

```
$ sudo lvm
lvm> 
```

### :round_pushpin: Other Commands

       lvm(8) lvm.conf(5) lvmconfig(8)

       pvchange(8)  pvck(8)  pvcreate(8) pvdisplay(8) pvmove(8) pvremove(8) pvresize(8) pvs(8)
       pvscan(8)

       vgcfgbackup(8) vgcfgrestore(8)  vgchange(8)  vgck(8)  vgcreate(8)  vgconvert(8)  vgdis‐
       play(8)  vgexport(8)  vgextend(8)  vgimport(8) vgimportclone(8) vgmerge(8) vgmknodes(8)
       vgreduce(8) vgremove(8) vgrename(8) vgs(8) vgscan(8) vgsplit(8)

       lvcreate(8) lvchange(8) lvconvert(8) lvdisplay(8) lvextend(8)  lvreduce(8)  lvremove(8)
       lvrename(8) lvresize(8) lvs(8) lvscan(8)

       lvm-fullreport(8)   lvm-lvpoll(8)  lvm2-activation-generator(8)  blkdeactivate(8)  lvm‐
       dump(8)

       dmeventd(8) lvmpolld(8) lvmlockd(8) lvmlockctl(8) cmirrord(8) lvmdbusd(8)

       lvmsystemid(7) lvmreport(7) lvmraid(7) lvmthin(7) lvmcache(7)


## :gear: Install lmv2

```
$ sudo apt-get install lvm2
```

# References

:strawberry: https://raspberrypi.stackexchange.com/questions/85958/easy-backups-and-snapshots-of-a-running-system-with-lvm
