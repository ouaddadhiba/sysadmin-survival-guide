 # 🔴 Issue #9: GRUB Not Loading (Linux)

 # 🚨 GRUB Boot Crisis: Rapid Recovery Protocol
> **When the screen is black and the clock is ticking. A zero-fluff field manual for sysadmins.**

---

## 🎯 Executive Summary: The 90-Second Diagnosis

**Answer these two questions immediately:**

1.  **What do you see?**
    - `grub rescue>` prompt → **JUMP TO: [TACTIC A: GRUB Rescue](#-tactic-a-grub-rescue-mode-immediate-boot)**
    - Black screen / BIOS loop → **JUMP TO: [TACTIC B: Live USB Reinstall](#-tactic-b-live-usb-grub-reinstall-full-recovery)**

2.  **Is this UEFI or Legacy BIOS?**
    - Boot Live USB → Open Terminal → `ls /sys/firmware/efi`
    - **If directory EXISTS:** UEFI System. *Use `efibootmgr`.*
    - **If directory MISSING:** Legacy BIOS System. *Use `grub-install /dev/sdX`.*

> ⚡ **This guide is linear. Follow the flowchart below.**

```
Boot Failure
    ↓
Screen Output?
    ↓
grub rescue> prompt → TACTIC A: Immediate Boot Attempt → Success? → Yes → RUN TACTIC B to PermaFix
    ↓                                                                   →
Black/Empty Screen → TACTIC B: Live USB Recovery → Mode? → UEFI → UEFI Protocol → SYSTEM RECOVERED
                                                                        ↓
                                                                  BIOS → BIOS Protocol → SYSTEM RECOVERED
```

---

## 🧰 The Kit: Non-Negotiable Prerequisites

- **A Live Linux USB** (SystemRescue, Ubuntu, Fedora). *Ventoy multi-ISO USB is ideal.*
- **Terminal Access.** This is a command-line operation.
- **Root Privileges.** `sudo` is your best friend.

---

## 🔥 TACTIC A: GRUB Rescue Mode (Immediate Boot)

*// OBJECTIVE: Bypass the failure and boot the system NOW. Then, apply a permanent fix.*

**You are at the `grub rescue>` prompt.**

1.  **Find your boot partition:**
    ```
    grub rescue> ls
    # Lists devices, e.g., (hd0), (hd0,msdos1), (hd0,gpt1)...
    ```

2.  **Probe each partition to find `/boot/grub`:**
    ```
    grub rescue> ls (hd0,msdos2)/boot/grub
    # If you see file listings, this is your partition. If 'unknown filesystem', try another.
    ```

3.  **Set the root and prefix:**
    ```
    grub rescue> set root=(hd0,msdos2)
    grub rescue> set prefix=(hd0,msdos2)/boot/grub
    ```

4.  **Load the normal module and boot:**
    ```
    grub rescue> insmod normal
    grub rescue> normal
    ```

✅ **IF SUCCESSFUL:** The system will boot. **IMMEDIATELY open a terminal and run TACTIC B to make the fix permanent.**

❌ **IF FAILED:** The GRUB installation is too damaged. Proceed to TACTIC B.

---

## 💻 TACTIC B: Live USB GRUB Reinstall (Full Recovery)

*// OBJECTIVE: Chroot into the installed system and surgically reinstall the bootloader.*

### Phase 1: Intelligence Gathering (Live USB Environment)

1.  **Boot from Live USB.** Choose "Try" or "Rescue" mode.
2.  **Identify Boot Mode:**
    ```bash
    ls /sys/firmware/efi # Check for UEFI
    ```
3.  **Reconnaissance: Find your partitions.**
    ```bash
    sudo lsblk -f # Shows partitions with filesystems, better than fdisk -l
    # OR use the classic:
    sudo fdisk -l
    ```
    **Identify:**
    - `sda2`: Root (`/`) partition (ext4, btrfs, etc.)
    - `sda1`: EFI System Partition (ESP) (vfat) - *UEFI only*
    - `sda3`: Separate `/boot` partition (ext4) - *Optional*

### Phase 2: Mount and Enter (The Chroot)

*Replace `/dev/sda2` and `/dev/sda1` with your actual partitions.*

```bash
# 1. Mount the root partition
sudo mount /dev/sda2 /mnt

# 2. Mount the ESP (UEFI Systems ONLY)
sudo mount /dev/sda1 /mnt/boot/efi

# 3. Mount critical virtual filesystems
sudo mount --bind /dev /mnt/dev
sudo mount --bind /dev/pts /mnt/dev/pts
sudo mount --bind /proc /mnt/proc
sudo mount --bind /sys /mnt/sys
sudo mount --bind /run /mnt/run

# 4. Chroot into the system
sudo chroot /mnt
```
*You are now inside your broken system as root.*

### Phase 3: The Surgery (Reinstall GRUB)

#### **PROTOCOL UEFI:**
```bash
# Reinstall GRUB to the ESP
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=LINUX --recheck

# Recreate the GRUB config
update-grub

# OPTIONAL BUT CRITICAL: Ensure the EFI entry is correct.
efibootmgr -c -d /dev/sda -p 1 -L "LINUX" -l \\EFI\\LINUX\\grubx64.efi
```

#### **PROTOCOL LEGACY BIOS:**
```bash
# Reinstall GRUB to the MBR of the disk
grub-install --target=i386-pc --recheck /dev/sda

# Recreate the GRUB config
update-grub
```

### Phase 4: Exfiltration and Validation

```bash
# Exit the chroot environment
exit

# Unmount all partitions (optional, but clean)
sudo umount -R /mnt

# Reboot the system
sudo reboot
```
**Remove the Live USB when the system restarts.**

---

## 🚑 Advanced Triage: When Standard Ops Fail

- **`error: unknown filesystem`**
  - **Root Cause:** GRUB modules missing or corrupt
  - **Countermeasure:** Boot from Live USB, `chroot`, reinstall `grub-efi-amd64-signed` (Ubuntu) or equivalent package

- **`error: no such partition`**  
  - **Root Cause:** Partition table changed, UUID mismatch
  - **Countermeasure:** 
    1. Check UUIDs in `/etc/fstab` and `/boot/grub/grub.cfg`
    2. Verify with `tune2fs -l /dev/sda2 | grep UUID`
    3. Update GRUB config with `update-grub`

- **Boots directly to Windows**
  - **Root Cause:** Windows update nuked the EFI entry
  - **Countermeasure:** `chroot` into Linux, use `efibootmgr -o 0000,0001` to set Linux as first boot option

- **Dual-boot: Windows Fast Startup**
  - **Root Cause:** Windows hibernates the disk, locking it
  - **Countermeasure:** Boot into Windows → Power Options → "Choose what power buttons do" → Turn off "Fast Startup"

---

## 📜 The One-Line Emergency Script (Copy-Paste Salvation)

*For when your brain is fried. Run this from the Live USB terminal after identifying your root partition as `/dev/sda2` and ESP as `/dev/sda1`.*

```bash
# UEFI SYSTEMS - THE NUCLEAR OPTION (Copy-Paste Entire Block)
sudo mount /dev/sda2 /mnt && \
sudo mount /dev/sda1 /mnt/boot/efi && \
sudo mount --bind /dev /mnt/dev && sudo mount --bind /dev/pts /mnt/dev/pts && \
sudo mount --bind /proc /mnt/proc && sudo mount --bind /sys /mnt/sys && \
sudo mount --bind /run /mnt/run && \
sudo chroot /mnt /bin/bash -c "grub-install --efi-directory=/boot/efi && update-grub && exit" && \
sudo reboot
```

---

## 📋 Quick Reference Field Card

**UEFI Reinstall**
- `grub-install --target=x86_64-efi --efi-directory=/boot/efi`

**BIOS Reinstall** 
- `grub-install /dev/sda`

**Update Config**
- `update-grub`

**View Boot Order**
- `efibootmgr`

**Check Partitions**
- `lsblk -f`

**Mount Sequence**
```bash
sudo mount /dev/sda2 /mnt
sudo mount /dev/sda1 /mnt/boot/efi  # UEFI only
sudo mount --bind /dev /mnt/dev
sudo mount --bind /proc /mnt/proc
sudo mount --bind /sys /mnt/sys
sudo chroot /mnt
```

---

## ✅ After-Action Report: Prevention & Hardening

**Automate GRUB Updates**
- Add a hook to run `update-grub` after kernel updates

**Backup Your ESP**
- `tar czf ~/esp-backup.tar.gz /boot/efi`

**Dual-Boot Sanctity** 
- In Windows, **disable Fast Startup** forever

**Know Your `efibootmgr`**
- `sudo efibootmgr -v` is your UEFI crystal ball

**Regular Health Checks**
- Periodically verify boot functionality
- Keep Live USB rescue media updated
- Document your partition layout

---

## 🆘 Emergency Contacts & Resources

**Official Documentation**
- [Arch Wiki: GRUB](https://wiki.archlinux.org/title/GRUB) - The ultimate technical reference
- [Ubuntu Community: GRUB Repair](https://help.ubuntu.com/community/Grub2) - Distro-specific guidance

**Rescue Tools**
- [SystemRescue](https://www.system-rescue.org/) - Professional recovery live CD
- [Ventoy](https://www.ventoy.net/) - Multi-ISO bootable USB creator

**Community Support**
- [Unix & Linux Stack Exchange](https://unix.stackexchange.com/) - Expert troubleshooting community
- Your distribution's forums - Distro-specific help
