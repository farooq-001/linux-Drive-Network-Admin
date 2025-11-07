
# 🧩 1. Hardware & Driver Information
#CPU Info
lscpu                     # Show CPU architecture and virtualization support
cat /proc/cpuinfo         # Detailed CPU info

#Memory Info
free -h                   # Memory usage
cat /proc/meminfo         # Detailed RAM info
dmidecode -t memory       # Physical memory module details

#Disk & Storage
lsblk                     # List block devices (disks and partitions)
lsblk -o NAME,MODEL,SIZE,ROTA,TYPE,MOUNTPOINT
lshw -class disk          # Disk hardware details
sudo fdisk -l             # Show partitions and disk layout
sudo smartctl -a /dev/sda # SSD/HDD health check (requires smartmontools)

#PCI / USB Devices
lspci                     # List PCI devices (e.g., NICs, GPUs)
lspci -v                  # Verbose PCI info (shows kernel drivers)
lsusb                     # List USB devices
lsusb -v                  # Detailed USB device info

#Kernel Modules (Drivers)
lsmod                     # List loaded kernel modules (drivers)
modinfo <module_name>     # Show detailed info about a module
sudo modprobe <module>    # Load a kernel module
sudo modprobe -r <module> # Remove a module

# ⚙️ 2. System Administration Commands
ip addr show             # Show all network interfaces and IPs
ip link show             # Show NICs and status
ip route show            # Show routing table
nmcli device status      # NetworkManager device status
ethtool eth0             # NIC driver, speed, and duplex info
sudo ethtool -i eth0     # Show NIC driver name and version

# 🔋 4. Hardware Monitoring
sensors                  # Show temperature and fan speeds (requires lm-sensors)
sudo htop                # Interactive process monitor
sudo iostat -xz 1        # Disk I/O performance (requires sysstat)
sudo vmstat 1            # Memory, I/O, and CPU stats

# 🧱 5. Boot & Kernel Management
dmesg | less              # Kernel boot messages
dmesg | grep -i error     # Look for hardware or driver errors
lsinitrd | less           # Show initramfs contents
sudo grub2-mkconfig -o /boot/grub2/grub.cfg   # Regenerate GRUB config

# 🔍 6. Driver Installation & Detection
sudo lshw -short | grep -i driver
sudo ubuntu-drivers list             # (Ubuntu) List available drivers
sudo ubuntu-drivers autoinstall      # Auto-install recommended drivers
On RHEL/CentOS:
sudo dnf install kernel-modules-extra

# 🧰 7. System Management & Maintenance
top                        # View running processes
df -h                      # Disk space usage
du -sh /var/log/*          # Folder size usage
journalctl -xe             # System logs
uptime                     # System uptime and load
who                        # Logged-in users
ps aux                     # Running processes
kill -9 <pid>              # Force stop a process




