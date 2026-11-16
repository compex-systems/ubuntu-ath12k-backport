# Qualcomm ath12k Backport Guide for Ubuntu

This repository provides patches and instructions to compile and install the Qualcomm `ath12k` Wi-Fi 7 driver on Ubuntu using OpenWrt Linux `backports`.

## Supported Hardware

- **Compex Wi-Fi 7000 Series** (Qualcomm QCN9274)
- Tested on **Ubuntu 22.04 LTS** (Kernel `5.15` and `6.1`)

## Repository Structure

| Target Kernel | Backports Version | Directory |
| :--- | :--- | :--- |
| **Linux 5.15** | `backports-6.12.6` | [`v5.15/backport_6.12.6`](./v5.15/backport_6.12.6/) |
| **Linux 5.15** | `backports-6.9.9` | [`v5.15/backport_6.9.9`](./v5.15/backport_6.9.9/) |
| **Linux 6.1** | `backports-6.9.9` | [`v6.1/backport_6.9.9`](./v6.1/backport_6.9.9/) |
