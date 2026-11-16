# ath12k Backport for Kernel 5.15
This repository provides patches and instructions to backport the Qualcomm ath12k wireless driver to Linux Kernel 5.15 using the backports-6.12.6 source.

## Support Hardware
* Compex Wi-Fi 7000 series(QCN9274)
* Tested on Ubuntu 22.04 with mainline Kernel 5.15

## 1. Prerequisites
Ensure you have the necessary build tools and kernel headers installed:
```bash
sudo apt update
sudo apt install build-essential linux-headers-$(uname -r) wget
```

## 2. Download Backports Source
```bash
wget https://mirror2.openwrt.org/sources/backports-6.12.6.tar.xz
tar -xvf backports-6.12.6.tar.xz
```

## 3. Apply Patches
```bash
cp -r patches /to/your/path/backports-6.12.6
cd backports-6.12.6
patch -p1 < patches/0001-build-add-ath12k-deconfig.patch
patch -p1 < patches/0002-Fix-compile-error.patch
patch -p1 < patches/0003-ath12k-remove-redundant-regulatory-rules-intersection-logic-in-host.diff
patch -p1 < patches/0004-fix-net-compatibility-errors.patch
patch -p1 < patches/0005-fix-mhi-issues.patch
```

## 4. Build and Install
```bash
cd backports-6.12.6
make defconfig-ath12k
make 
sudo make INSTALL_MOD_STRIP=1 install
reboot
```

## 5. Verification
```bash
modinfo ath12k
```

---
```bash
How to uninstall backport ath12k:
cd backports-6.12.6
make uninstall 
make clean
reboot
```
