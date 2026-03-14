# Hardware Information about my Dell R710

<p align="center">
  <img src="../images/r710fr.jpeg" width="350">
  <img src="../images/r710top.jpeg" width="350">
</p>

## Overview
This server is currently used as a virtualization and Active Directory lab machine.

## Hardware Specs

CPU: 2x Xeon X5650 @ 2.67 GHz
RAM: 144GB DDR3 ECC  
RAID: PERC H700
Drives: 6x SAS - Not currently used 

## Planned Usage

- Active Directory Domain Controller
- Virtual networking labs
- CCNA practice environment

## Lab Log

### 2026 February
- Purchased server
- Verified POST
- Checks Caddys, CPU, RAM and condition

- Powered on for first full inspection
- Entered BIOS
- Verified RAID configuration

### 2026 March

#### March 13
- Configured local peer-to-peer network between Tailscale node and iDRAC6 Express
- Configured BIOS and Lifecycle Controller
- Worked on stabilizing iDRAC6 web interface (configured Java 6, TLS settings, Internet Explorer compatibility)
- Received and installed iDRAC6 Enterprise card
- Reconfigured iDRAC to use the dedicated iDRAC NIC
- Removed DVD drive, for SSD
- Received, configured, and installed Samsung 850 EVO 250GB SSD via SATA-Slim → SATA adapter
- Installed Proxmox VE remotely using iDRAC remote console

  Notes:
- iDRAC6 requires legacy TLS and Java 6 for the web console
- Modern browsers must use IE or other older browser with adjustments

  Extra:
- Received RAM holder
