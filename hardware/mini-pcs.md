# Mini PC Nodes

Two small form factor PCs are used as remote nodes in my homelab.  
Both systems run Tailscale to allow secure remote access between devices in the lab.

These nodes provide lightweight services such as file access and camera monitoring.

## Hardware

| Device | Model | CPU | RAM | Storage | Role |
|------|------|------|------|------|------|
| Node 1 | Dell Optiplex Micro | Intel i5 | 8GB | 256GB NVMe | File access / NAS access |
| Node 2 | Lenovo ThinkCentre Tiny | Intel i5 | 8GB | 256GB NVMe | Camera monitoring |

## Purpose

These nodes allow services in the homelab to be accessed remotely using a private mesh VPN.

The setup allows secure remote access without exposing services directly to the public internet.

## Services

### File Access Node

- Connected to a QNAP NAS
- Provides remote access to files
- Used for personal file storage and photo backups

### Camera Monitoring Node

- Runs Agent DVR
- Connects to an IP camera
- Used for monitoring and recording

## Storage

### NAS

- 2-bay QNAP NAS
- RAID1 configuration
- 2 × 2TB drives

The NAS is used for:

- photo storage
- file storage
- remote file access

## Remote Access Architecture

Remote access to the homelab is handled through a private mesh VPN using Tailscale.

This allows all systems in the lab to communicate over a secure private network without exposing services to the public internet or requiring port forwarding.

## Goals

- Secure remote access to lab infrastructure
- Avoid exposing services directly to the internet
- Allow remote management of servers and network devices
- Provide access to storage and monitoring services

## Devices Connected to the VPN

- Personal workstation
- Two Mini PC nodes
- NAS
- Homelab servers

These devices form a private network that can be accessed from anywhere once authenticated.

## Management Access

This setup allows remote access to internal services such as:

- Server management interfaces
- NAS file access
- Camera monitoring
- Infrastructure administration (e.g., iDRAC)

All management traffic stays inside the VPN network rather than being exposed publicly.
