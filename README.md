<div align="center">

![WarpGate banner](docs/assets/banner.svg)

# WarpGate

Raspberry Pi Cloudflare WARP gateway

![License](https://img.shields.io/badge/license-MIT-brightgreen)
![Language](https://img.shields.io/badge/language-Shell-blue)
</div>

---

<p align="center">
  <img src="docs/screenshots/dashboard.png" alt="WarpGate preview" width="90%">
</p>

<br>

---

## Features

- **Secure Tunneling** — Route all traffic through Cloudflare WARP.
- **DNS Privacy** — DNS resolution via Cloudflare (1.1.1.1 / 1.0.0.1).
- **WiFi Access Point** — Internal hotspot with DHCP (hostapd + dnsmasq).
- **Outbound Proxy** — Transparent NAT proxy for all network devices.
- **Raspberry Pi** — Optimized for Pi 4/5.
- **Zero Config** — Automatic WARP registration.
- **Dashboard** — Live status web UI with WebSocket updates.
- **Telegram Bot** — Remote control: status, WARP toggle, service restarts.

## Requirements

- Raspberry Pi 4/5 (or any Debian-based host) with a wired WAN uplink (`eth0`) and a WiFi adapter (`wlan0`)
- Root privileges — all setup scripts must run under `sudo`
- The Cloudflare WARP client is installed automatically by the installer
- Optional: a Telegram bot token + your chat ID for remote control

## Quick Start

### Raspberry Pi

```bash
git clone https://github.com/OneByJorah/WarpGate.git
cd WarpGate

# 1. Edit 01_install.sh to set your AP_SSID / AP_PASS / AP_IP
sudo bash 01_install.sh      # base system: packages, hostapd, dnsmasq, iptables, WARP
sudo bash 02_configure.sh    # dashboard, Telegram bot, systemd units
sudo reboot
```

### Dashboard Only (Docker)

```bash
cp .env.example .env
# edit .env if needed, then:
docker compose up -d
```

### Check Status

```bash
warp-cli status
```

## Configuration

All settings live in `/etc/EdgeGateway/config.env` (written by the installer; see [.env.example](.env.example) for a template):

| Variable | Default | Description |
|----------|---------|-------------|
| `AP_IFACE` | `wlan0` | WiFi interface used as access point |
| `WAN_IFACE` | `eth0` | Wired uplink interface |
| `AP_SSID` | `PiGateway` | Hotspot network name |
| `AP_PASS` | *(set in installer)* | Hotspot passphrase — change it |
| `AP_COUNTRY` | `US` | Regulatory domain (2-letter code) |
| `AP_IP` | `192.168.50.1` | Gateway IP on the AP subnet |
| `AP_SUBNET` | `192.168.50.0/24` | AP subnet |
| `WARP_MTU` | `1280` | WARP tunnel MTU |
| `DASHBOARD_PORT` | `5000` | Dashboard web port |
| `BOT_TOKEN` | *(empty)* | Telegram bot token (optional) |
| `ADMIN_CHAT_ID` | *(empty)* | Telegram admin chat ID(s), comma-separated |

## Architecture

```
Devices ──Gateway──▶ WarpGate ──WARP──▶ Cloudflare ──▶ Internet
                        │
                        ├──▶ DNS Privacy
                        ├──▶ Traffic Encryption
                        └──▶ Dashboard
```

## Project Structure

```
WarpGate/
├── 01_install.sh            # Base install: packages, AP, firewall, WARP client
├── 02_configure.sh          # Dashboard + Telegram bot + systemd units
├── dashboard.py             # Flask dashboard (deployed by 02_configure.sh)
├── templates/               # Dashboard HTML
│   └── dashboard.html
├── Dockerfile               # Dashboard-only container build
├── docker-compose.yml       # Dashboard container orchestration
└── .env.example             # Config variable reference
```

## Contributing

Contributions are welcome. Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for community standards.

## Security

For security concerns, see [SECURITY.md](SECURITY.md). Please report vulnerabilities privately via GitHub Security Advisories — do not use public issues.

## License

[MIT License](LICENSE) © Jhonattan L. Jimenez (OneByJorah)

---

<p align="center">Built with 🌴 by <a href="https://github.com/OneByJorah">OneByJorah</a> · <a href="https://jorahone.com">jorahone.com</a></p>
