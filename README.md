# linux_swap_increase
Guide to increase swap memory 
sudo swapoff -a 

sudo fallocate -l 1G /swapfile

ls -lh /swapfile

-rw-r--r-- 1 root root 1.0G Apr 25 11:14 /swapfile

sudo chmod 600 /swapfile

ls -lh /swapfile

sudo mkswap /swapfile

sudo swapon /swapfile

sudo swapon --show

free -h

sudo cp /etc/fstab /etc/fstab.bak

echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab

cat /proc/sys/vm/swappiness

sudo sysctl vm.swappiness=60

sudo nano /etc/sysctl.conf

vm.swappiness=60

cat /proc/sys/vm/vfs_cache_pressure

sudo sysctl vm.vfs_cache_pressure=50

sudo nano /etc/sysctl.conf

vm.vfs_cache_pressure=50
