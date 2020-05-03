# profit-trailer-dc

This is a clone of Jakkie! All creedits to Jakkie!

Donations to Jakkie are welcome `https://hub.docker.com/r/jakkie/profit-trailer-docker`

Profit Trailer Docker

[![Docker Pulls](https://img.shields.io/docker/pulls/moli87/profit-trailer-dc.svg?label=pulls&logo=docker&logoColor=FFFFFF)](https://hub.docker.com/r/moli87/profit-trailer-dc/)
[![Docker Stars](https://img.shields.io/docker/stars/moli87/profit-trailer-dc.svg?label=stars&logo=docker&logoColor=FFFFFF)](https://hub.docker.com/r/moli87/profit-trailer-dc/)
[![](https://images.microbadger.com/badges/image/moli87/profit-trailer-dc.svg)](https://microbadger.com/images/moli87/profit-trailer-dc/ "Get your own image badge on microbadger.com")
[![](https://images.microbadger.com/badges/version/moli87/profit-trailer-dc.svg)](https://microbadger.com/images/moli87/profit-trailer-dc/ "Get your own version badge on microbadger.com")
[![Docker Build Status](https://img.shields.io/docker/cloud/build/moli87/profit-trailer-dc.svg?label=build&logo=docker&logoColor=FFFFFF)](https://hub.docker.com/r/moli87/profit-trailer-dc/)

Compatible with Profit Trailer bot version : v2.4.27
`https://wiki.profittrailer.com/doku.php?id=start`

## Install Docker

- Windows `https://docs.docker.com/toolbox/toolbox_install_windows/`
- Mac OS `https://docs.docker.com/docker-for-mac/install/`
- Linux Ubuntu `https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-docker-ce`

## Quick Guide

### Run latest Profit Trailer version

- Download and edit application.properties with your license key and exchange apis, other wise the bot will not start. See for `https://wiki.profittrailer.com/doku.php?id=start` reference.
- To Run Container and replace `/path/to/""` with the full path where the application.properties file and data folder are.

### docker

```bash
docker create \
  --name=pt-profit-trailer \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/Zurich \
  -p 8081:8081 \
  -v /path/to/profittrailer/application.properties:/app/ProfitTrailer/application.properties \
  -v /path/to/profittrailer-data:/app/ProfitTrailer/data \
  -v /path/to/profittrailer-logs:/app/ProfitTrailerlogs \
  --restart unless-stopped \
  moli87/profit-trailer-dc
```

### docker-compose

Compatible with docker-compose v3 schemas

```bash
---
version: '3'

services:
  profittrailer:
    image: moli87/profit-trailer-dc
    container_name: profit-trailer
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Europe/Zurich
    volumes:
      - ./application.properties:/app/ProfitTrailer/application.properties
      - ./data:/app/ProfitTrailer/data
      - ./logs:/app/ProfitTrailerlogs
    restart: unless-stopped
    ports:
      - "8081:8081"
```
If you like it, support appreciated!

BTC: 17cqx7P6aRn9egZfSkzbyNqKjd3Xm6W9T4

BCH: qq020gjmrd83rfaut4fzrncc8ejlv32q4yuhnzgc5c

BNB: bnb1m6fn76pplwf3pwem62ghcpryruu0kmnmrmsq22

ETH: 0x4B2895914147787d0C15868F86c460aF6Fb45D91

LTC: LbvRzuBrF4eVrEC2zkHveQAxEyfaNBAa3j

XMR: 45sS3GEkui1LosH14zvnvwChqEy8sK4pJXWAax1VvSD9BSN9qUsAuzsVwoTrvMjFndS9LpYpGBpCwY9JxifzxAW16wWsAAY
