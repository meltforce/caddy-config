# caddy-config

Caddyfile configuration for the homelab internal reverse proxy.

## How it works

This repo is automatically pulled by [git-sync](https://github.com/kubernetes/git-sync) sidecars running alongside Caddy on two LXC containers (`caddy-lab-01`, `caddy-lab-02`). Caddy's `--watch` flag picks up changes after each sync.

## Deployment

- **Sync interval**: every 5 minutes
- **HA**: both nodes serve independently via Tailscale Services
- **TLS**: wildcard certificates via Cloudflare DNS challenge
- **Ansible**: infrastructure managed in the `homelab` repo under `configuration/caddy-internal/`

## Usage

Edit the `Caddyfile`, push to `main`, and both nodes pick up changes automatically.
