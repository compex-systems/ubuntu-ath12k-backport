# Qualcomm ath12k Backport Guide for Ubuntu

This repository provides patches and instructions to compile and install the Qualcomm `ath12k` Wi-Fi 7 driver on Ubuntu using OpenWrt Linux `backports`.

## Supported Hardware

- **Compex Wi-Fi 7000 Series** (Qualcomm QCN9274)
- Tested on **Ubuntu 22.04 LTS** (Kernel `5.15` and `6.1`)

## Branches

Select the branch matching your target Linux kernel version (`uname -r`):

| Target Kernel | Branch | Included Backports |
| :--- | :--- | :--- |
| **Linux 5.15** | [`v5.15`](https://github.com/compex-systems/ubuntu-ath12k-backport/tree/v5.15) | `backport_6.9.9`, `backport_6.12.6` |
| **Linux 6.1** | [`v6.1`](https://github.com/compex-systems/ubuntu-ath12k-backport/tree/v6.1) | `backport_6.9.9` |
