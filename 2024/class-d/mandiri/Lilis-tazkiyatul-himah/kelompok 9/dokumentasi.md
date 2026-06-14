# Arch Linux Install
iwctl
station wlan0 get-networks
station wlan0 connect <namawifi>
exit

cryptsetup luksFormat /dev/sda7
cryptsetup luksOpen /dev/sda7 lilis

pvcreate /dev/mapper/lilis
vgcreate level /dev/mapper/lilis

lvcreate -L 10G level -n root
lvcreate -L 10G level -n vars
lvcreate -L 1G level -n vlog
lvcreate -L 1G level -n vaud
lvcreate -L 1G level -n vtmp
lvcreate -L 10G level -n home
lvcreate -l100%FREE level -n dock


