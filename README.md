[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/stasadev/ddev-redis-insight/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/stasadev/ddev-redis-insight/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/stasadev/ddev-redis-insight)](https://github.com/stasadev/ddev-redis-insight/commits)
[![release](https://img.shields.io/github/v/release/stasadev/ddev-redis-insight)](https://github.com/stasadev/ddev-redis-insight/releases/latest)

# DDEV Redis Insight

## Overview

[Redis Insight](https://redis.io/insight/) is a visual tool that provides capabilities to design, develop, and optimize your Redis application. Query, analyse and interact with your Redis data.

This add-on integrates Redis Insight into your [DDEV](https://ddev.com/) project.

## Requirements

Before installing this add-on, the [Redis service](https://github.com/ddev/ddev-redis) must be available:

```bash
ddev add-on get ddev/ddev-redis
```

## Installation

```bash
ddev add-on get stasadev/ddev-redis-insight
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

| Command | Description |
| ------- | ----------- |
| `ddev redis-insight` | Open Redis Insight in your browser (`https://<project>.ddev.site:5540`) |
| `ddev describe` | View service status and used ports for Redis Insight |
| `ddev logs -s redis-insight` | Check Redis Insight logs |

## Advanced Customization

You may need to adjust the password depending on your Redis configuration:

* A `docker-compose.redis-insight_password.yaml` file is automatically created on install, if we detect that Redis needs one.
* By default, the password is set via `REDIS_PASSWORD=redis` in that file. If you modify it, be sure to remove the `#ddev-generated` comment to prevent your changes from being overwritten.

To change the Docker image:

```bash
ddev dotenv set .ddev/.env.redis-insight --redis-insight-docker-image="redis/redisinsight:latest"
ddev add-on get stasadev/ddev-redis-insight
ddev restart
```

Make sure to commit the `.ddev/.env.redis-insight` file to version control.

All customization options (use with caution):

| Variable | Flag | Default |
| -------- | ---- | ------- |
| `REDIS_INSIGHT_DOCKER_IMAGE` | `--redis-insight-docker-image` | `redis/redisinsight:latest` |

## Credits

**Contributed and maintained by [@stasadev](https://github.com/stasadev)**
