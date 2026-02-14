# cfg-mgt-dev
Developing configuration management for linux desktop fleet.

# Endpoint Baseline (Ansible Pull) — Ubuntu 24.04 LTS

This repo provides a fork-ready starting point for Linux endpoint configuration management using Ansible in **pull mode**.

## Why pull mode?
Roaming laptops (home, coffee shop, etc.) are often unreachable inbound. `ansible-pull` flips the model: endpoints periodically pull this repo and apply the baseline locally.

## Quick start (subscribe a laptop)
On the endpoint:

```bash
curl -fsSL https://raw.githubusercontent.com/armstrma/cfg-mgt-dev/main/scripts/subscribe.sh | sudo bash -s -- \
  --repo https://github.com/<ORG>/<REPO>.git \
  --branch main \
  --interval 6h

