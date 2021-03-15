
cd /home/hpsp/rock_space/qemu/initrd
dd if=/dev/zero of=initrd_64le.ext4 bs=1M count=30
mkfs.ext4 initrd_64le.ext4
mkdir -p mount
sudo mount initrd_64le.ext4 ./mount/
cp ./mount_bakcp/*  ./mount -rf  


