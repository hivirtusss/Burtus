# OnePlus 9R (LE2101) — ReSukiSU + SUSFS Flash Guide

**Device:** OnePlus 9R lemonades  
**Stock OS:** OxygenOS 14.0.0.2401 (Android 14)  
**Kernel zip:** `OnePlus-9R-LE2101-ReSukiSU-SUSFS-AnyKernel3.zip`

## Pehle download karo

| File | Link |
|------|------|
| Kernel (yeh zip) | Isi folder ka `OnePlus-9R-LE2101-ReSukiSU-SUSFS-AnyKernel3.zip` |
| ReSukiSU Manager | https://github.com/cctv18/ReSukiSU_CI/releases/latest |
| Kernel Flasher 1.6.0 | https://github.com/fatalcoder524/KernelFlasher/releases/download/v1.6.0/KernelFlasher_1.6.0.apk |
| SUSFS Module | https://github.com/sidex15/susfs4ksu-module/releases/download/v1.5.2+_R27/ksu_module_susfs_1.5.2+.zip |

## Flash steps

1. **Backup** — Kernel Flasher se backup lo: `boot`, `init_boot`, `vendor_boot`, `dtbo`, `vbmeta`
2. **APatch hatao** — stock boot restore karo dono slots pe
3. **ReSukiSU Manager** install karo
4. **Kernel Flasher** install karo, root access do
5. Active slot select karo (A ya B)
6. **Flash → Flash AK3 Zip** → `OnePlus-9R-LE2101-ReSukiSU-SUSFS-AnyKernel3.zip`
7. Reboot
8. ReSukiSU Manager → **Modules** → SUSFS module flash karo
9. Reboot — SuSFS activated ✅ dikhna chahiye

## Bootloop ho to

Kernel Flasher se backup restore karo ya fastboot:
```bash
fastboot flash boot_a stock_boot.img
fastboot flash boot_b stock_boot.img
```

## Note

Yeh kernel JackA1ltman ke ReSukiSU + SUSFS build se hai (SM8250 / OP8 series, OOS13.1 base).  
9R pe kaam karta hai kyunki same chip (Snapdragon 870) aur AnyKernel3 sirf `boot` partition update karta hai.

OOS14-specific build workflow is repo branch `cursor/op9r-resukisu-kernel-3144` par available hai.
