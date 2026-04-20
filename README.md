#ath12k Backport for Kernel 5.15
This repository provides patches and instructions to backport the Qualcomm ath12k wireless driver to Linux Kernel 5.15 using the backports-6.9.9 source.

##Support Hardware
* Compex Wi-Fi 7000 series(QCN9274)
* Tested on Ubuntu 22.04 with mainline Kernel 5.15

##1. Prerequisites
Ensure you have the necessary build tools and kernel headers installed:
```bash
sudo apt update
sudo apt install build-essential linux-headers-$(uname -r) wget
```

##2. Download Backports Source
```bash
wget https://mirror2.openwrt.org/sources/backports-6.9.9.tar.xz
tar -xvf backports-6.9.9.tar.xz
```

##3. Apply Patches
```bash
cd backports-6.9.9
patch -p1 < patches/0001-patching.patch
patch -p1 < patches/0002-build-add-ath12k-deconfig.patch
patch -p1 < patches/0003-build-add-config-use-kernel-regdb-key.patch
patch -p1 < patches/0004-Fix-timer.h-build-error.patch
patch -p1 < patches/0005-Fix-ath12k-driver-build-error-for-5.15.patch
patch -p1 < patches/0006-Fix-wireless-build-error-for-5.15.patch
patch -p1 < patches/0007-Fix-mhi-build-error-for-5.15.patch
patch -p1 < patches/0008-Fix-bss-conf-build-error-for-5.15.patch
patch -p1 < patches/982-wifi-ath12k-add-dualmac-module-parameter.patch
patch -p1 < patches/9002-wifi-ath12k-fix-ath12k_hw_ring_mask_qcn9274.patch
patch -p1 < patches/v2-wifi-ath12k-enable-service-flag-for-survey-dump-stats.patch
patch -p1 < patches/1-2-wifi-ath12k-fix-BSS-chan-info-request-WMI-command.patch
patch -p1 < patches/2-2-wifi-ath12k-match-WMI-BSS-chan-info-structure-with-firmware-definition.patch
```

##4. Build and Install
```bash
cd backports-6.9.9
make defconfig-ath12k
make 
sudo make INSTALL_MOD_STRIP=1 install
reboot
```

##5. Verification
```bash
modinfo ath12k
```

---
```bash
How to uninstall backport ath12k:
cd backports-6.9.9
make uninstall 
make clean
reboot
```
