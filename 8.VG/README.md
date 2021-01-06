# Volume Group


https://www.digitalocean.com/community/tutorials/how-to-use-lvm-to-manage-storage-devices-on-ubuntu-16-04

https://www.digitalocean.com/community/tutorials/an-introduction-to-lvm-concepts-terminology-and-operations

## :a: Listing PV, VG, LV

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

`scan` option scans the system and outputs minimal information about the `volumes` it finds

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
