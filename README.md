Ubuntu Bootable ISO scripts
===========================

Install Prereq
--------------

sudo apt install squashfs-tools genisoimage

Mount your ISO

sudo mount -o loop ubuntu-9.04-desktop-i386.iso mnt

Copy Contents

mkdir extract-cd
sudo rsync --exclude=/casper/filesystem.squashfs -a mnt/ extract-cd

Extract the squshfs

sudo unsquashfs mnt/casper/filesystem.squashfs
sudo mv squashfs-root edit

Create Chroot
sudo chroot edit

You can now make any changes you wish and then just run the build-cd.sh script to compile the ISO.
