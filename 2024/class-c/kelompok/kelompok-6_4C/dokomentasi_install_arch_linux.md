# Cara Installasi Dekstop Arch Linux
Jika sudah masuk ke dalam base linux, ikuti di bawah ini:

## Formating
``` 
Root
```
Masukin Password

Cek Connect Wifi
```
iwctl
```
station wlan0 connect (nama wifi)  
(abis itu dicek, buat udah ter-connect wifi belum)
```
exit
```
```
ping 8.8.8.8
```
## Instal KDE Plasma 
```
pacman -S plasma networkmanager piperwire dolphin kitty
```
jika terjadi eror : 
<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/c28a04bf-171d-4011-9b9a-7c433047ce02" />
```
systemctl restart systemd - resolved
```
```
systemctl restart iwd
```
```
connect wifi lagi
```
kalau sudah, instal lagi KDE plasma

jika sudah terinstal :
masukin usseradd 
```
usseradd -m  (nama usser)
```
```
password (nama usser) (masukin passwordnya)
```

lalu masuk ke KDE plasma
```
sudo systemctl enable --now sddm
```
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/64fca410-3726-4210-b6db-23962afb77b4" />


# Untuk Aktifin Networkmanager 
buka terminal, lalu ketik 
```
su -
```
lalu masukin password root
```
systemctl start NetworkManager
```
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/8786dcaf-21dc-4103-b971-a47c6139c892" />
