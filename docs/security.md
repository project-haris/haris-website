---
title: Haris Security Model
description: Security model for Haris maritime telemetry with encrypted Tailscale transport, fail-closed firewalls, local buffering, and operational controls.
keywords:
  - maritime telemetry security
  - Haris security
  - Tailscale maritime
  - vessel data security
  - edge device hardening
---

# Security

Haris is presented as a secure system because the security model is layered. It does not depend on one control.

## Transport Protection

Traffic is expected to move over an encrypted Tailscale tunnel so internal services are not exposed directly to the public internet.

## Resilience Under Degraded Links

The platform continues collecting and buffering locally during connectivity loss, then synchronizes once a trusted path returns.

## Physical Compromise Awareness

Physical compromise is part of the threat model. Deployment notes, enclosure controls, tamper assumptions, and hardened services reduce the blast radius if the device is touched.

## Operational Controls

- Restricted exposed services
- Fail-closed firewall assumptions
- Health monitoring for the node itself
- Reproducible deployment with infrastructure as code
