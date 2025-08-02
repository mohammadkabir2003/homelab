# 🏡 Home Lab Server Setup

This is my home lab project using an old HP laptop running Ubuntu Server 24.04 LTS. It includes static IP setup, OpenSSH configuration, remote access, and system hardening.

## 🔧 Features

- Ubuntu Server 24.04 LTS (no GUI)
- Static IP address via router reservation
- OpenSSH server (port 22)
- Ethernet over WiFi
- External remote access tested with No-IP
- Lid closed = SSH kept alive

## ⚙️ Specs

- HP Pavilion laptop
- 750 GB HDD (ext4)
- Ethernet MAC: `74:46:A0:79:E1:4F`
- Static IP: `192.168.1.160`

### 🛠️ Problems Faced and Fixes Applied

| Problem                             | Fix                                                                 |
|-------------------------------------|----------------------------------------------------------------------|
| SSH timeout when lid closes         | Edited `logind.conf` and set `HandleLidSwitch=ignore`               |
| Dynamic IP resets                   | Set static DHCP reservation on Verizon router                       |
| SSH not on port 22                  | Reconfigured `sshd_config` to allow custom port                     |
| DDNS not updating automatically     | Created DDNS key and linked it to router DDNS client                |
| SSH fails from outside home network | Set up port forwarding (e.g., external 2222 → internal 22)          |
| SSH connection reset via hotspot    | Enabled remote access on router and allowed necessary firewall ports|
| UFW blocking SSH                    | Allowed SSH port via `sudo ufw allow <port>` and enabled UFW        |
