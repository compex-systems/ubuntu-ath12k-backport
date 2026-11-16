# Qualcomm ath12k Backport Guide for Ubuntu

Many production and LTS systems stay on older Linux kernels for stability rather than performing a full kernel upgrade. Using OpenWrt `backports`, this repository provides compatibility patches and build instructions to bring newer upstream Qualcomm `ath12k` Wi-Fi 7 drivers and features onto those stable kernels.

## Supported Hardware

- **Compex Wi-Fi 7000 Series** (Qualcomm QCN9274)
- Tested on **Ubuntu 22.04 LTS** (Kernel `5.15` and `6.1`)

## Repository Structure

| Target Kernel | Backports Version | Directory |
| :--- | :--- | :--- |
| **Linux 5.15** | `backports-6.12.6` | [`v5.15/backport_6.12.6`](./v5.15/backport_6.12.6/) |
| **Linux 5.15** | `backports-6.9.9` | [`v5.15/backport_6.9.9`](./v5.15/backport_6.9.9/) |
| **Linux 6.1** | `backports-6.9.9` | [`v6.1/backport_6.9.9`](./v6.1/backport_6.9.9/) |
