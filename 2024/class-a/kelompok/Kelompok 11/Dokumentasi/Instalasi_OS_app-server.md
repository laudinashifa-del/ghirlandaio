# Install OS App Server

## 1. Rekam Instalasi (Opsional)

```bash
asciinema rec nama.cast
```

---

## 2. Koneksi Wi-Fi

```bash
iwctl
```

```bash
station wlan0 get-networks
```

```bash
station wlan0 connect nama_wifi
```

Masukkan password Wi-Fi lalu:

```bash
exit
```

Cek koneksi:

```bash
ping 8.8.8.8
```

---

## 3. Install Arch Linux (Amanda Blackbird)

```bash
sudo pacman -Syu

```bash
sudo pacman -S linux-hardened linux-hardened-headers

