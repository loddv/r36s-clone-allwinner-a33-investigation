I can provide a backup of the sd img if someone need it.

# R36S Clone Investigation (Allwinner-based)

This repository documents an investigation of a handheld console sold as "R36S"
which is NOT based on RK3326, but on an Allwinner SoC running EmuELEC.

## Key findings

- System: EmuELEC 4.7 (SquashFS SYSTEM image)
- Kernel drivers: sunxi (Allwinner), not Rockchip
- Not compatible with ArkOS
- Uses SYSTEM squashfs instead of ext4 rootfs

## Why ArkOS does not boot

ArkOS expects:
- RK3326 SoC
- ext4 root filesystem
- Rockchip DTB

This device provides:
- Allwinner kernel
- SquashFS SYSTEM image
- Custom bootloader

## Other

My board is GA36-MB v1.1-20251025.
I think the chip is an Allwinner A33.

ArkOS cannot be installed without rebuilding:
- kernel
- bootloader
- device tree

I couldn't find any .dtb in the emuelec because of the way they adapted it to the A33.

The picture of the disk manager from windows is exactly how it looks when I restore the img backup, from there I deleted some games to make it easier to work with it.

## Goal

Help users identify fake / clone R36S devices and avoid incompatible OS installs.




