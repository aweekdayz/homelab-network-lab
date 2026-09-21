# N100 Proxmox and OpenWrt Homelab

An Intel N100-based environment for virtualization, routing, storage, DNS, remote access, and Linux services.

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

## Stack

- Proxmox VE virtualization on an N100 x86 system
- An iStoreOS/OpenWrt routing environment with DHCP, NAT, and IPv4/IPv6 configuration
- AdGuard Home for DNS filtering
- Tailscale remote access, including subnet routing, exit-node use, and access-control settings
- OpenMediaVault and Linux container services
- SSH and command-line administration for deployment, routine maintenance, and configuration validation
