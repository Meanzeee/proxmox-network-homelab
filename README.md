# proxmox-network-homelab
# Virtualized Network & Infrastructure Homelab

**Tech Stack:** Proxmox VE 9.2.2, Debian Linux, KVM/QEMU, Linux Bridge, LVM-thin, Tailscale VPN, Ubuntu Desktop, EVE-NG

## Project Overview

A self-hosted virtualization and networking lab built on dedicated desktop hardware to practice Linux system administration, network infrastructure, remote server management, and virtual network simulation.

The lab is designed to support hands-on learning in networking, system integration, virtualization, and network security.

## Hardware

- CPU: Intel Core i5-9400F (6 cores / 6 threads)
- RAM: 16 GB DDR4
- Hypervisor storage: KINGFAST 240 GB SSD
- Host networking: Intel Ethernet NIC
- Client: Windows laptop for web-based remote administration

## Architecture

- **Hypervisor:** Proxmox VE installed directly on dedicated hardware
- **Management network:** 192.168.200.0/24
- **Virtual switch:** Linux Bridge (vmbr0)
- **Storage:** Local directory and LVM-thin
- **Remote access:** Tailscale VPN over HTTPS
- **Power management:** Remote shutdown and LAN-based Wake-on-LAN

## Completed Implementation

### 1. Hypervisor Deployment

- Installed Proxmox VE on dedicated SSD hardware using UEFI boot.
- Maintained Windows and Proxmox installations on separate physical drives.
- Configured host networking and verified hardware resources.
- Configured Proxmox no-subscription APT repository after resolving HTTP 401 authentication errors.

### 2. Virtual Networking

- Configured static IPv4 addressing, default gateway, and DNS.
- Verified the physical NIC and Linux Bridge (vmbr0).
- Configured VirtIO network adapters for virtual machines.

### 3. Secure Remote Administration

- Installed and configured Tailscale VPN on the Proxmox host.
- Verified remote access from an external mobile hotspot network.
- Accessed the Proxmox management interface securely over HTTPS without exposing the management port directly to the public Internet.

### 4. Power Management

- Verified Ethernet Wake-on-LAN capability using ethtool.
- Successfully powered on the physical server using a Magic Packet from the local network.
- Tested remote shutdown through the Proxmox management interface.

### 5. Virtual Machine Provisioning

- Created Ubuntu Desktop VM (2 vCPU, 4 GB RAM, 35 GiB virtual disk).
- Created EVE-NG VM (4 vCPU, 6 GB RAM, 60 GiB virtual disk).
- Configured virtual CPU, memory, firmware, storage, and networking for both virtual machines.

## Troubleshooting Experience

- Resolved UEFI/Secure Boot-related USB boot issues.
- Diagnosed Proxmox APT repository authentication errors.
- Distinguished LAN addressing from Tailscale overlay addressing.
- Verified Wake-on-LAN behavior after host shutdown.
- Inspected disk devices and mount points to safely identify removable storage.

## Planned Work

- Complete Ubuntu Desktop and EVE-NG guest OS installation.
- Validate KVM nested virtualization for EVE-NG.
- Deploy Cisco IOSv/IOSvL2 network topologies.
- Practice VLAN, inter-VLAN routing, OSPF, BGP and ACLs.
- Explore virtual network segmentation and firewall rules.
- Configure SSH-based Linux administration.
- Implement VM backups, snapshots and recovery tests.
- Introduce network automation and infrastructure monitoring.

## Learning Outcomes

- Bare-metal hypervisor deployment
- Linux administration fundamentals
- Virtual networking and storage
- Secure remote infrastructure access
- VM resource allocation and provisioning
- Basic troubleshooting across network and system layers

## Status

**Phase 1:** Proxmox deployment, management networking, VPN and power management completed.

**Phase 2:** Ubuntu Desktop and EVE-NG VM installation and network lab development in progress.
