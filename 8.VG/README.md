# Volume Group


https://www.digitalocean.com/community/tutorials/how-to-use-lvm-to-manage-storage-devices-on-ubuntu-16-04

https://www.digitalocean.com/community/tutorials/an-introduction-to-lvm-concepts-terminology-and-operations


## :one: Physical Volume

```
$ sudo pvs
  PV         VG        Fmt  Attr PSize    PFree   
  /dev/sda3  ubuntu-vg lvm2 a--  <272.40g <136.20g
```


## :two: Volume Group

```
$ sudo vgs
  VG        #PV #LV #SN Attr   VSize    VFree   
  ubuntu-vg   1   1   0 wz--n- <272.40g <136.20g
```

## :three: Logical Volume

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
