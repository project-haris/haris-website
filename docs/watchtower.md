---
title: Watchtower Ansible Automation
description: Watchtower provisions Haris vessel edge nodes and M-SOC core services with Ansible playbooks for Signal K, harisd, Filebeat, ELK, Tailscale, and Zabbix.
keywords:
  - Watchtower Ansible
  - Haris deployment
  - maritime Ansible automation
  - vessel edge provisioning
  - M-SOC infrastructure
---

# Watchtower

Watchtower is the Ansible automation layer for Project Haris vessel edge nodes and M-SOC core services. It provisions edge devices, deploys the Haris data collector and Signal K stack, and configures the onshore ELK pipeline that receives `haris_signalk` events.

## Operational Scope

<div class="feature-grid">
  <div class="feature-card">
    <h3>Vessel Edge</h3>
    <p>Installs Signal K, harisd, Node-RED, Filebeat, Tailscale, Zabbix agent, firewall policy, user management, time sync, and CAN interface setup.</p>
  </div>
  <div class="feature-card">
    <h3>M-SOC Core</h3>
    <p>Deploys Elasticsearch, Logstash, Kibana, Zabbix server, Docker-ready services, firewall policy, Tailscale access, and supporting host roles.</p>
  </div>
</div>

## Data Path

```text
Vessel sensors / NMEA
  -> Signal K on haris-sinilind
  -> harisd / data_aggregator.py
  -> /opt/haris/logs/signalk_snapshots.jsonl
  -> Filebeat
  -> Tailscale encrypted tunnel
  -> Logstash on haris-citadel:5044
  -> Elasticsearch
  -> Kibana
```

Watchtower also keeps the legacy direct TCP path available when enabled: `harisd` can forward newline-delimited JSON events to Logstash on TCP `5045`.

## Primary Playbooks

```bash
ansible-playbook playbooks/group_vessel_edge/main.yml -D
ansible-playbook playbooks/group_msoc_core/main.yml -D
```

## Targeted Runs

```bash
ansible-playbook playbooks/group_vessel_edge/main.yml -l haris-sinilind -t haris -D
ansible-playbook playbooks/group_vessel_edge/main.yml -l haris-sinilind -t nodered -D
ansible-playbook playbooks/group_msoc_core/main.yml -l haris-citadel -t elk_stack -D
```

## Key Roles

- `haris` deploys Signal K and the `harisd` collector on vessel devices.
- `nodered` installs Node-RED on Debian-based edge devices.
- `elk_stack` deploys Elasticsearch, Logstash, and Kibana on core nodes.
- `zabbix_agent` and `zabbix_server` provide node and core monitoring.
- `artis3n.tailscale.machine` installs and authenticates Tailscale where VPN reachability is required.

## Repository

Watchtower source: <https://github.com/project-haris/watchtower>
