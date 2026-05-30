---
title: Project Haris Repositories
description: Source repositories for Project Haris, including marine_haris, Watchtower automation, and the haris.ahmdngi.io documentation site.
keywords:
  - Project Haris repositories
  - marine_haris
  - Watchtower repository
  - maritime open source
---

# Repos

The Haris workspace is a set of focused sub-projects.

## `marine_haris`

Python-based vessel edge stack covering parsers, transmission, health monitoring, hardware notes, deployment guides, and system services.

## `watchtower`

Ansible automation for vessel edge devices and M-SOC core services, including Haris deployment, Tailscale, ELK, Node-RED, and supporting system roles.

Repository: <https://github.com/project-haris/watchtower>

### Roles managed for vessel-edge nodes

- `sysctl` - kernel and system tuning
- `users_groups` - local users and group management
- `sshd` - SSH server configuration
- `soft_apt` - Debian package installation baseline
- `mullvad_browser` - Mullvad Browser deployment
- `firewalld` - host firewall rules
- `resolv_hosts` - hostname and resolver entries
- `artis3n.tailscale.machine` - Tailscale client setup
- `cron` - scheduled task management
- `haris` - Haris collector and Signal K integration
- `nodered` - Node-RED installation and setup
- `chrony` - time synchronization
- `zabbix_agent` - node monitoring agent

### Roles managed for M-SOC core nodes

- `sysctl` - kernel and system tuning
- `users_groups` - local users and group management
- `sshd` - SSH server configuration
- `soft_yum` - RPM-based package installation baseline
- `firewalld` - host firewall rules
- `resolv_hosts` - hostname and resolver entries
- `artis3n.tailscale.machine` - Tailscale client setup
- `cron` - scheduled task management
- `chrony` - time synchronization
- `zabbix_agent` - node monitoring agent
- `zabbix_server` when enabled - central Zabbix server stack
- `elk_stack` when enabled - Elasticsearch, Logstash, and Kibana
- `docker` when enabled - container runtime installation

## `haris.ahmdngi.io`

Static marketing site. This Zensical folder reframes the same project as a documentation-first presentation that can be served with `zensical serve`.
