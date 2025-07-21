[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/stasadev/ddev-redis-insight/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/stasadev/ddev-redis-insight/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/stasadev/ddev-redis-insight)](https://github.com/stasadev/ddev-redis-insight/commits)
[![release](https://img.shields.io/github/v/release/stasadev/ddev-redis-insight)](https://github.com/stasadev/ddev-redis-insight/releases/latest)

# DDEV Redis Insight

## Overview

This add-on integrates Redis Insight into your [DDEV](https://ddev.com/) project.

## Installation

```bash
ddev add-on get stasadev/ddev-redis-insight
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

| Command | Description |
| ------- | ----------- |
| `ddev describe` | View service status and used ports for Redis Insight |
| `ddev logs -s redis-insight` | Check Redis Insight logs |

## Advanced Customization

To change the Docker image:

```bash
ddev dotenv set .ddev/.env.redis-insight --redis-insight-docker-image="busybox:stable"
ddev add-on get stasadev/ddev-redis-insight
ddev restart
```

Make sure to commit the `.ddev/.env.redis-insight` file to version control.

All customization options (use with caution):

| Variable | Flag | Default |
| -------- | ---- | ------- |
| `REDIS_INSIGHT_DOCKER_IMAGE` | `--redis-insight-docker-image` | `busybox:stable` |

## Credits

**Contributed and maintained by [@stasadev](https://github.com/stasadev)**
