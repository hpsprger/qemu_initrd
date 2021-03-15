
cd /home/hpsp/rock_space/qemu/initrd
dd if=/dev/zero of=initrd_64le.ext4 bs=1M count=30
mkfs.ext4 initrd_64le.ext4
mkdir -p mount
sudo mount initrd_64le.ext4 ./mount/
cp ./mount_backup/*  ./mount -rf  


cd /home/hpsp/rock_space/qemu/initrd/mount
sudo cp /usr/aarch64-linux-gnu/lib   /home/hpsp/rock_space/qemu/initrd/mount -rf
sudo rm ./lib/*.a -rf
sudo rm ./lib/*.o -rf
sudo mkdir -p  proc sys tmp root var mnt dev etc  usr/local/bin 
sudo mknod dev/tty1 c 4 1 
sudo mknod dev/tty2 c 4 2 
sudo mknod dev/tty3 c 4 3 
sudo mknod dev/tty4 c 4 4 
sudo mknod dev/console c 5 1 
sudo mknod dev/null  c 1 3 

