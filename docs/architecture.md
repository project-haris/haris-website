---
title: Haris Architecture
description: Architecture for Haris maritime telemetry with Raspberry Pi 5, PiCAN-M, Signal K, harisd, Tailscale, Filebeat, Logstash, Elasticsearch, and Kibana.
keywords:
  - maritime telemetry architecture
  - Signal K architecture
  - NMEA 2000
  - vessel edge computing
  - ELK maritime observability
---

# Architecture

Haris is built as an edge-first maritime telemetry system. The core idea is simple: process high-value vessel data on the node, then move only the data that should leave the vessel over protected transport.

## Hardware Layer

- Raspberry Pi 5 with NVMe storage as the compute node
- PiCAN-M HAT for NMEA 2000 and NMEA 0183 connectivity
- TP-Link NX200 as the cellular gateway
- Protected vessel-side installation in a dry enclosure

## Software Layer

- Signal K services for normalization and local APIs
- `harisd` and parser modules for vessel telemetry collection
- Local JSONL or database buffering for degraded-link resilience
- Systemd services for repeatable operation and recovery

## Core Services

- Tailscale for encrypted transport and private reachability
- Filebeat, Logstash, Elasticsearch, and Kibana for observability
- Ansible automation via Watchtower for reproducible deployment
- Zabbix and system health checks for node monitoring

## High-Level Flow

```text
Vessel sensors / NMEA
  -> PiCAN-M HAT
  -> Raspberry Pi 5
  -> Signal K + harisd
  -> Local storage / buffering
  -> Tailscale encrypted tunnel
  -> Logstash / Elasticsearch / Kibana
  -> Maritime Security Operations Center
```

## Why Edge-First Matters

The platform keeps collecting and processing during degraded connectivity. That lowers operational fragility, reduces unnecessary data transfer, and makes the node useful even when uplinks are unstable.
