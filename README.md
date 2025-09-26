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
- [✅] #1: System won’t power on  
- [✅] #2: No display after power-on (black screen)  
- [✅] #3: “No bootable device” error  
- [✅] #4: Boot loop (repeated restarts)  
- [✅] #5: Beep codes during POST 
- [🟡] #6: BIOS/UEFI not detecting hard drive  
- [✅] #7: Corrupted firmware/UEFI settings  
- [🟡] #8: Boot from wrong device (e.g., USB stuck in boot order)  
- [✅] #9: GRUB not loading (Linux)  
- [🟡] #10: Windows Boot Manager missing or corrupted  
- [🟡] #11: Kernel panic (Linux/macOS)  
- [🟡] #12: Blue Screen of Death (BSOD) on startup  
- [🟡] #13: Stuck at manufacturer logo  
- [🟡] #14: Slow boot time (1+ minutes)  
- [🟡] #15: Fast startup causing boot issues (Windows)  

---

### 💾 Disk & File System Issues (16–30)  
- [🟡] #16: “Disk is full” error despite available space  
- [🟡] #17: File system corruption (e.g., ext4, NTFS)  
- [🟡] #18: Drive not showing up in File Explorer / lsblk  
- [🟡] #19: Permission denied when accessing files  
- [🟡] #20: Inability to write to external drive (read-only)  
- [🟡] #21: Mounting failure (wrong fstab entry, UUID changed)  
- [🟡] #22: Disk read/write errors (bad sectors)  
- [🟡] #23: SMART failure warnings  
- [🟡] #24: Accidental partition deletion  
- [🟡] #25: Encrypted drive won’t unlock (LUKS, BitLocker)  
- [🟡] #26: Swap partition not active  
- [🟡] #27: RAID array degraded or failed  
- [🟡] #28: “Invalid MBR” or “Invalid partition table”  
- [🟡] #29: Hidden recovery partition causing confusion  
- [🟡] #30: Slow disk performance (HDD vs SSD misidentified)  

---

### 🌐 Network & Connectivity (31–50)  
- [🟡] #31: No internet connection (Wi-Fi or Ethernet)  
- [🟡] #32: Connected to Wi-Fi but no internet  
- [🟡] #33: IP address conflict  
- [🟡] #34: DHCP not assigning IP  
- [🟡] #35: DNS resolution failure (can’t reach websites by name)  
- [🟡] #36: High latency or packet loss  
- [🟡] #37: Intermittent disconnections  
- [🟡] #38: Can ping but can’t browse (firewall blocking ports)  
- [🟡] #39: Proxy settings causing connection issues  
- [🟡] #40: Port blocked (e.g., 80, 443, 22)  
- [🟡] #41: SSH connection refused  
- [🟡] #42: RDP not working (port 3389 blocked)  
- [🟡] #43: Wi-Fi drops under load  
- [🟡] #44: Network adapter not recognized  
- [🟡] #45: Driver issues with NIC/Wi-Fi card  
- [🟡] #46: IPv6 misconfiguration  
- [🟡] #47: NAT/router issues in home networks  
- [🟡] #48: VPN connection fails or drops  
- [🟡] #49: Slow transfer speeds over LAN/WAN  
- [🟡] #50: MAC address filtering blocking device  

---

### 🧠 Memory, CPU & Performance (51–65)  
- [🟡] #51: System freezing or unresponsive  
- [🟡] #52: High CPU usage by unknown process  
- [🟡] #53: High memory (RAM) consumption  
- [🟡] #54: Constant swapping/paging (disk thrashing)  
- [🟡] #55: Fan running at 100% constantly  
- [🟡] #56: Overheating warnings or shutdowns  
- [🟡] #57: “Out of memory” error (OOM killer in Linux)  
- [🟡] #58: Background processes consuming resources  
- [🟡] #59: Slow application launch times  
- [🟡] #60: System lags when multiple apps open  
- [🟡] #61: Memory leak in application/service  
- [🟡] #62: Incorrect CPU frequency scaling  
- [🟡] #63: BIOS not recognizing full RAM capacity  
- [🟡] #64: ECC memory errors logged  
- [🟡] #65: Virtual memory/pagefile misconfigured (Windows)  

---

### 📁 User, Permissions & Environment (66–80)  
- [🟡] #66: User profile corrupted (Windows)  
- [🟡] #67: “Access denied” despite being admin  
- [🟡] #68: Home directory not mounting (Linux)  
- [🟡] #69: PATH environment variable missing key entries  
- [🟡] #70: Default shell not loading (e.g., .bashrc not sourced)  
- [🟡] #71: Roaming profile sync failure (enterprise)  
- [🟡] #72: Permission inheritance broken  
- [🟡] #73: Sudo not working (user not in sudoers)  
- [🟡] #74: UAC prompts too frequent or missing  
- [🟡] #75: SELinux/AppArmor blocking legitimate apps  
- [🟡] #76: Incorrect locale/timezone settings  
- [🟡] #77: Temporary files filling /tmp or %TEMP%  
- [🟡] #78: Orphaned lock files preventing app startup  
- [🟡] #79: Home folder ownership incorrect (Linux)  
- [🟡] #80: Profile loads slowly due to bloated registry/startup  

---

### 🧪 Services, Daemons & Processes (81–90)  
- [🟡] #81: Critical service failed to start (e.g., DHCP, Print Spooler)  
- [🟡] #82: systemd unit failing with active (failed)  
- [🟡] #83: Windows service stuck in “Stopping” state  
- [🟡] #84: Cron job not running  
- [🟡] #85: LaunchAgent/LaunchDaemon not loading (macOS)  
- [🟡] #86: Port already in use (e.g., “Address already in use”)  
- [🟡] #87: Dependency failure (service A needs service B)  
- [🟡] #88: Service running but not responding  
- [🟡] #89: Log rotation failure filling disk  
- [🟡] #90: Background update process hanging  

---

### 🔐 Security & Authentication (91–100)  
- [🟡] #91: Forgotten password / locked account  
- [🟡] #92: Two-factor authentication (2FA) lockout  
- [🟡] #93: Certificate errors (e.g., “Your connection is not private”)  
- [🟡] #94: TLS handshake failure  
- [🟡] #95: Antivirus quarantining legitimate software  
- [🟡] #96: Firewall blocking application silently  
- [🟡] #97: Group Policy preventing software install (Windows)  
- [🟡] #98: Smart card or biometric login failure  
- [🟡] #99: Expired security certificate on internal server  
- [🟡] #100: BitLocker recovery required (TPM failure or boot change)   



---

## 🤝 How to Contribute

We're building this guide together — every fix counts!

## Contact

For any questions or suggestions, please contact us at [houaddad@gmail.com] or [mkarima784@gmail.com]
