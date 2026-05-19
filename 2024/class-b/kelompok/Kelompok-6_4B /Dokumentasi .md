## 1. Mengaktifkan Layanan Jaringan Internet 

### Ketik perintah berikut untuk masuk  ke konsol interaktif:

```
iwctl
```

```
[iwd]# device list
```

```
[iwd]# station wlan0 scan
```

```
 [iwd]# station wlan0 get-networks
```
```
[iwd]# station wlan0 connect "Nama_WiFi_Pengguna"
``` 

### Verifikasi Koneksi : 
```
ping -c 3 google.com
```

## 2. Membuat Pengguna Baru (user) 
```
(useradd -m -G wheel -s /bin/bash kelompok6)
```

## 3. Memberikan proteksi sandi akun 
```
passwd kelompok6
```

## 4. Install Semua Package 
```
pacman -S networkmanager plasma sddm pipewire pipewire-alsa pipewire-pulse pipewire-jack wireplumber dolphin kitty
```

### Mengaktifkan Layanan Jaringan
```
systemctl enable NetworkManager
```
### Aktivasi Layar Login Grafis (SDDM)
```
systemctl enable sddm
```

## 5. Hak Akses Administrator Sudo
```
EDITOR=nvim visudo
```
## 6. Membangun ulang (rebuild) citra ramdisk awal untuk semua kernel Linux yang terpasang

```
mkinitcpio -P
```








