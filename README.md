# luks-grub-install
```shell
sudo mount /dev/mapper/vgname /mnt
sudo mount /dev/sdXY /mnt/boot
sudo mount /dev/sdXY /mnt/boot/efi
sudo mount --bind /dev /mnt/dev
sudo mount --bind /dev/pts /mnt/dev/pts
sudo mount --bind /proc /mnt/proc
sudo mount --bind /sys /mnt/sys
sudo mount --bind /run /mnt/run
sudo chroot /mnt

nano /etc/crypttab
-> lvname UUID=ab-cd none luks

apt-get install --reinstall grub-efi-amd64
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=grub
update-initramfs -k all -c -v
update-grub
```
