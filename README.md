# 🛠️ SYSADMIN SURVIVOR GUIDE

*A collaborative guide by Karima Mandili and Hiba Ouaddad*

> 🔧 Practical solutions to common technical issues — from boot failures to network problems, performance bottlenecks, and security hurdles.

This handbook is being built step by step to document reliable fixes for real-world IT, system administration, and desktop support challenges.  
We're starting with the most common issues and expanding over time.

---

## 📚 Table of Contents

Below are the chapters and key issues we’re documenting.  
✅ = In progress or completed  
🟡 = Coming soon

---

### 🔌 Hardware & Boot Issues (1–15)
- [🟡] System won’t power on  
- [🟡] Beep codes during POST  
- [🟡] “No bootable device” error  
- [🟡] Corrupted firmware/UEFI settings  
- [🟡] GRUB not loading (Linux)  
- [🟡] Windows Boot Manager missing or corrupted  
- [🟡] Kernel panic (Linux/macOS)  
- [🟡] Boot loop (repeated restarts)  
- [🟡] No display after power-on (black screen)  
- [🟡] Stuck at manufacturer logo  
- [🟡] Slow boot time (1+ minutes)  
- [🟡] Fast startup causing boot issues (Windows)  

---

### 💾 Disk & File System Issues (16–30)
- [🟡] File system corruption (e.g., ext4, NTFS)  
- [🟡] Permission denied when accessing files  
- [🟡] Mounting failure (wrong fstab entry, UUID changed)  
- [🟡] SMART failure warnings  
- [🟡] Encrypted drive won’t unlock (LUKS, BitLocker)  
- [🟡] RAID array degraded or failed  
- [🟡] “Disk is full” error despite available space  
- [🟡] Drive not showing up in File Explorer / lsblk  
- [🟡] Inability to write to external drive (read-only)  
- [🟡] Disk read/write errors (bad sectors)  
- [🟡] Accidental partition deletion  
- [🟡] “Invalid MBR” or “Invalid partition table”  
- [🟡] Hidden recovery partition causing confusion  
- [🟡] Slow disk performance (HDD vs SSD misidentified)  
- [🟡] Swap partition not active  

---

### 🌐 Network & Connectivity (31–50)
- [🟡] No internet connection (Wi-Fi or Ethernet)  
- [🟡] DNS resolution failure (can’t reach websites by name)  
- [🟡] Intermittent disconnections  
- [🟡] SSH connection refused  
- [🟡] Driver issues with NIC/Wi-Fi card  
- [🟡] NAT/router issues in home networks  
- [🟡] Connected to Wi-Fi but no internet  
- [🟡] IP address conflict  
- [🟡] DHCP not assigning IP  
- [🟡] High latency or packet loss  
- [🟡] Can ping but can’t browse (firewall blocking ports)  
- [🟡] Proxy settings causing connection issues  
- [🟡] Port blocked (e.g., 80, 443, 22)  
- [🟡] RDP not working (port 3389 blocked)  
- [🟡] Wi-Fi drops under load  
- [🟡] IPv6 misconfiguration  
- [🟡] VPN connection fails or drops  
- [🟡] Slow transfer speeds over LAN/WAN  
- [🟡] MAC address filtering blocking device  

---

### 🧠 Memory, CPU & Performance (51–65)
- [🟡] System freezing or unresponsive  
- [🟡] High memory (RAM) consumption  
- [🟡] Fan running at 100% constantly  
- [🟡] “Out of memory” error (OOM killer in Linux)  
- [🟡] Slow application launch times  
- [🟡] Memory leak in application/service  
- [🟡] BIOS not recognizing full RAM capacity  
- [🟡] High CPU usage by unknown process  
- [🟡] Constant swapping/paging (disk thrashing)  
- [🟡] Overheating warnings or shutdowns  
- [🟡] Background processes consuming resources  
- [🟡] System lags when multiple apps open  
- [🟡] Incorrect CPU frequency scaling  
- [🟡] ECC memory errors logged  
- [🟡] Virtual memory/pagefile misconfigured (Windows)  

---

### 📁 User, Permissions & Environment (66–80)
- [🟡] “Access denied” despite being admin  
- [🟡] PATH environment variable missing key entries  
- [🟡] Sudo not working (user not in sudoers)  
- [🟡] SELinux/AppArmor blocking legitimate apps  
- [🟡] Temporary files filling /tmp or %TEMP%  
- [🟡] Home folder ownership incorrect (Linux)  
- [🟡] User profile corrupted (Windows)  
- [🟡] Home directory not mounting (Linux)  
- [🟡] Default shell not loading (e.g., .bashrc not sourced)  
- [🟡] Roaming profile sync failure (enterprise)  
- [🟡] Permission inheritance broken  
- [🟡] UAC prompts too frequent or missing  
- [🟡] Incorrect locale/timezone settings  
- [🟡] Orphaned lock files preventing app startup  
- [🟡] Profile loads slowly due to bloated registry/startup  

---

### 🧪 Services, Daemons & Processes (81–90)
- [🟡] Critical service failed to start (e.g., DHCP, Print Spooler)  
- [🟡] Windows service stuck in “Stopping” state  
- [🟡] Cron job not running  
- [🟡] Port already in use (e.g., “Address already in use”)  
- [🟡] Dependency failure (service A needs service B)  
- [🟡] Log rotation failure filling disk  
- [🟡] systemd unit failing with active (failed)  
- [🟡] LaunchAgent/LaunchDaemon not loading (macOS)  
- [🟡] Service running but not responding  
- [🟡] Background update process hanging  

---

### 🔐 Security & Authentication (91–100)
- [🟡] Forgotten password / locked account  
- [🟡] Certificate errors (e.g., “Your connection is not private”)  
- [🟡] Certificate errors (e.g., “Your connection is not private”)  
- [🟡] Antivirus quarantining legitimate software  
- [🟡] Group Policy preventing software install (Windows)  
- [🟡] Expired security certificate on internal server  
- [🟡] Two-factor authentication (2FA) lockout  
- [🟡] TLS handshake failure  
- [🟡] Firewall blocking application silently  
- [🟡] Smart card or biometric login failure  
- [🟡] BitLocker recovery required (TPM failure or boot change)  

---

## 🤝 How to Contribute

We're building this guide together — every fix counts!

## Contact

For any questions or suggestions, please contact us at [houaddad@gmail.com] or [mkarima784@gmail.com]
