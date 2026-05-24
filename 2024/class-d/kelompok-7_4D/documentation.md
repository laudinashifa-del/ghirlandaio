# CONNECT WIFI

```bash
iwctl
```
---
```bash
device list
```
#### Catatan : Untuk cek driver wifi setiap laptop
---
```bash
station (driver wifi) get-network
```
#### Catatan : untuk melihat jaringan yang tersedia
---
```bash
station (driver wifi) scan
```
#### Catatan : Untuk memindai jaringan yang ada
---
```bash
station {device wifi} connect "{nama wifi}"
```
```
exit
```
#### Catatan : Untuk menghubungkan ke jaringan yang sudah ditentukan

# Memeriksa jaringan 

```bash
ping 1.1.1.1
```
# jika sudah masuk kedalam install arch linux nya langsung ikutin langkah dibawah


****

# CHECKING PARTISI
## jika ingin melihat partisi beserta type nya
```
lsblk -o name,fstype,size 
```
## Jika ingin melihat partisinya saja
```
lsblk
```

## MEMBAGI PARTISI
```
cfdisk /dev/[partisi] (untuk membentuk layout yg mah di install)
```

### MINIMAL PARTISI 
#### **MENYESUAIKAN DENGAN PENYIMPANAN YANG ADA**
```
boot = 1G [EFI system]
root = 49G [linux filesystem/]
```

#### kalo salah satu partisi PENTING ke hapus, langsung QUIT aja jangan di WRITE

```
lsblk (lagi)
```
****
# partition
## setup lvm
```
pvcreate /dev/[partisi root]
```
```
vgcreate proc /dev/[partisi root]
```

### logical volume
```
lvcreate -L size (G | M) proc -n root
```
```
lvcreate -L size (G | M) proc -n vars
```
```
lvcreate -L size (G | M) proc -n vtmp
```
```
lvcreate -L size (G | M) proc -n vlog
```
```
lvcreate -L size (G | M) proc -n vaud
```
```
lvcreate -l50%FREE proc -n home
```
```
lvcreate -L size (G | M) proc -n [name]
```

## setup luks
```
cryptsetup luksFormat /dev/proc/[name]
```
```
cryptsetup luksOpen /dev/proc/ikhsan [nama device]
```
```
mkfs.ext4 /dev/mapper/[nama device]
```

## formating 
```
mkfs.ext4 /dev/proc/root
```

```
mkfs.vfat -F32 -n BOOT /dev/[partisi boot]
```

```
mkfs.ext4 /dev/proc/vars
```

```
mkfs.ext4 /dev/proc/vtmp
```

```
mkfs.ext4 /dev/proc/vlog
```

```
mkfs.ext4 /dev/proc/vaud
```

```
mkfs.ext4 /dev/proc/home
```

```
mkfs.ext4 /dev/proc/[name]
```
