<div align="center">

![WarpGate banner](docs/assets/banner.svg)

# WarpGate



[![GitHub release](https://img.shields.io/github/v/release/OneByJorah/WarpGate?color=34d399&label=release&logo=github)](https://github.com/OneByJorah/WarpGate/releases)
[![PyPI version](https://img.shields.io/pypi/v/warpgate?color=34d399&label=pip&logo=pypi)](https://pypi.org/project/warpgate/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://www.docker.com/)
[![Python 3.11+](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?color=FFB300&logo=open-source-initiative&logoColor=FFB300)](https://opensource.org/licenses/MIT)

</div>

![WarpGate screenshot](docs/assets/screenshot.png)

## What This Is

Lightweight API gateway and reverse proxy — rate limiting, auth hooks, request routing, and observability with Docker deployment.

Built for operators who want a self-hosted, Docker-deployed solution they control.

## Quick Start

### pip

```bash
pip install warpgate
```

### Docker (recommended)

```bash
git clone https://github.com/OneByJorah/WarpGate.git
cd WarpGate
docker compose up -d
```

### From Source

```bash
git clone https://github.com/OneByJorah/WarpGate.git
cd WarpGate
pip install -r requirements.txt
python3 app.py
```

## Install

### pip

```bash
pip install warpgate
```

### Docker

```bash
git clone https://github.com/OneByJorah/WarpGate.git
cd WarpGate
docker compose up -d
```

### From Source

```bash
git clone https://github.com/OneByJorah/WarpGate.git
cd WarpGate
pip install -r requirements.txt
python3 app.py
```

## Features

- **Self-hosted** — no cloud dependencies, run on your own hardware
- **Docker Compose** — full stack deployment with one command
- **pip package** — install via PyPI
- **Dark theme** — operational, clean UI

- **API gateway** — route and proxy API requests
- **Rate limiting** — per-endpoint and per-client limits
- **Auth hooks** — JWT and API key validation
- **Request routing** — path-based and header-based routing
- **Observability** — request logging and metrics
- **Docker deployment** — single container or compose
- **Dark theme** — operational, minimal UI

## Tech Stack

- **Backend** — Python 3.11+, pydantic, pyyaml
- **Deployment** — Docker Compose, pip install
- **Configuration** — environment variables, config files

## Package Badges

[![GitHub release](https://img.shields.io/github/v/release/OneByJorah/WarpGate?color=34d399&label=release&logo=github)](https://github.com/OneByJorah/WarpGate/releases)
[![PyPI version](https://img.shields.io/pypi/v/warpgate?color=34d399&label=pip&logo=pypi)](https://pypi.org/project/warpgate/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://www.docker.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?color=FFB300&logo=open-source-initiative&logoColor=FFB300)](https://opensource.org/licenses/MIT)

## Contributing

Contributions are welcome. [Open an issue](https://github.com/OneByJorah/WarpGate/issues) to report a bug or request a feature.

## License

MIT — see [LICENSE](LICENSE).
