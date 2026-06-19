# Instalasii Os Server
1. Melihat / Cek Partisi

   lsblk
   ```
2. Enskripsi Partisi (LUKS)
   
   cryptsetup luksFormat /dev/nvme0n1p6
# Ketik YES (kapital) untuk konfirmasi, lalu masukkan passphrase (Password)

cryptsetup luksOpen /dev/nvme0n1p6 proc
# Buka partisi terenkripsi dengan nama mapper "proc"
```
3. Setup LVM
```

pvcreate /dev/mapper/proc          
vgcreate saw /dev/mapper/proc      

# Buat Logical Volumes:
lvcreate -L 8G    saw -n root      
lvcreate -L 5G    saw -n vars      
lvcreate -L 1G    saw -n vlog
lvcreate -L 1G    saw -n vaud      
lvcreate -L 1.5G  saw -n vtmp      
lvcreate -l50%FREE saw -n home     
lvcreate -l100%FREE saw -n podman
```

4. Format
```

