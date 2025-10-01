# Microsoft-Office-On-Linux

Best way to install **Microsoft Office** and more Windows native apps (that you can't install with Wine) on Linux.  
This setup uses **Winboat**, **Docker**, and **QEMU** for a containerized Windows environment.

---

## Prerequisites

**Check if your CPU supports virtualization**

```bash
grep -E -c '(vmx|svm)' /proc/cpuinfo
```

If the output is greater than 0, virtualization is supported.
Make sure virtualization is enabled in your BIOS/UEFI.

**Install Required Packages**

```bash
sudo pacman -S docker qemu-full virt-manager dnsmasq bridge-utils
```

**Enable Docker**

```bash
sudo systemctl enable docker --now
```

**Install Docker Compose (V2)**

```bash
sudo pacman -S docker-compose
```

**Add Yourself to Docker Group**

```bash
sudo usermod -aG docker $USER
```

Log out and log back in for the changes to take effect.

**Install Winboat (from AUR)**

```bash 
paru -S winboat-bin
```

