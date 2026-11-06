# my-fucked-dbg-linux-distro

Minimalistic custom Linux distribution and kernel sandbox designed specifically for fast debugging, testing `rust-for-linux` modules, and driver development under QEMU.

## Features
- **Kernel:** Mainline Linux (`7.4.0-rc1`) with Rust support enabled.
- **Rootfs:** Ultra-lightweight BusyBox (`ash`) footprint (~12 MB disk, <50 MB RAM).
- **Architecture:** x86_64 (optimized for QEMU / KVM virtualization with host CPU pass-through).
- **Purpose:** Rapid kernel development loop (`compile -> boot -> dmesg -> debug`) without risking your host system.

## Quick Start
```bash
qemu-system-x86_64 -kernel bzImage -initrd rootfs.cpio -append "console=ttyS0" -nographic
