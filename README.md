# dd0c.pmx_install
Role for installing Proxmox.

#ROOTSERVER:

##Hardware data:
##  CPU1: AMD Ryzen 5 3600 6-Core Processor (Cores 12)
##  Memory: 64250 MB
##  Disk /dev/nvme0n1: 512 GB (=> 476 GiB) Disk /dev/nvme1n1: 512 GB (=> 476 GiB) Total capacity 953 GiB with 2 Disks
##  Network data: eth0 LINK: yes
##  MAC: a8:a1:59:8c:bf:ab
##  IP: 65.21.233.68 IPv6: 2a01:4f9:6a:202c::2/64 RealTek RTL-8169 Gigabit Ethernet driver

Disk partitioning:
  / 10G
  /boot 1G
  /home 10G
  /tmp 4G
  /usr 10G
  /var all
  /var/log 100G
  swap 4G

Errors after install Debian 12:
  1> Degraded performance, RAID 1 has to initialize the disk duplication
  $ cat /proc/mdstat
  2> W: Possible missing firmware /lib/firmware/rtl_nic/... for module r8169
  $ apt update $ apt install firmware-realtek firmware-misc-nonfree
