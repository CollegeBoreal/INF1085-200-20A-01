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

## :a: Scripting PV, VG, LV

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

## :b: Scanning PV, VG, LV

`??scan` option scans the system and outputs `minimal` information about the `volumes` it finds

### :round_pushpin: Physical Volume

### :round_pushpin: Volume Group

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
