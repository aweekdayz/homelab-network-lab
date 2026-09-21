# Homelab and Network Lab

This repository presents a personal network and systems environment built around an Intel N100 x86 host. It focuses on the architecture and technologies of systems that I maintain myself.

## Architecture

```mermaid
flowchart TD
    Internet[Upstream network] --> Router[iStoreOS / OpenWrt VM]
    Router --> LAN[Home LAN]
    Router --> Tailscale[Tailscale remote access]
    Router --> DNS[AdGuard Home DNS filtering]
    Proxmox[Proxmox VE on N100 host] --> Router
    Proxmox --> OMV[OpenMediaVault VM]
    Proxmox --> LXC[Linux container services]
    LAN --> Clients[Windows, macOS, mobile, and lab devices]
```

## Environment

- Proxmox VE virtualization on an N100 x86 system
- An iStoreOS/OpenWrt routing environment with DHCP, NAT, and IPv4/IPv6 configuration
- AdGuard Home for DNS filtering
- Tailscale remote access, including subnet routing, exit-node use, and access-control settings
- OpenMediaVault and Linux container services
- SSH and command-line administration for deployment, routine maintenance, and configuration validation

## Repository Scope

- `architecture.md` - hardware, virtual machines, and service relationships
- `configuration/` - sanitized configuration patterns and design decisions
- `operations/` - maintenance notes and validation procedures
