# uramdisk

# dd if=uramdisk.img of=ramdisk.img.gz skip=64 bs=1
# gunzip ramdisk.img.gz
# mkdir ramdisk; cd ramdisk
# cpio -i < ../ramdisk.img
<make any changes needed>

?
# find . | cpio --create --format='newc' | gzip > ../ramdisk.img
# mkimage -A arm -O linux -T ramdisk -C none -a LOADADDRESS -n "Label you want" -d ./ramdisk.img ./uramdisk.img
