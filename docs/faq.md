---
title: Haris FAQ
description: Answers about Haris vessel telemetry collection, edge processing, maritime security controls, degraded connectivity, and M-SOC integration.
keywords:
  - Haris FAQ
  - vessel telemetry FAQ
  - maritime edge platform
  - M-SOC integration
---

# FAQ

## What exactly does Haris collect and process on the vessel?

Haris is designed to ingest vessel telemetry from NMEA 0183, NMEA 2000, and Signal K compatible sources. It can normalize those inputs on the edge device, monitor local system health, and prepare selected data for controlled transmission toward the operations center.

## Why is Haris presented as a secure system?

The security model does not rely on one feature alone. Haris combines encrypted transport, fail-closed firewall assumptions, service isolation, monitored device health, and operational controls around deployment and physical access.

## How does Haris stay useful if the vessel link is unstable or intermittent?

The architecture is edge-first, which means collection and local processing happen on the vessel before any uplink is required. The node keeps ingesting, buffering, and monitoring even when connectivity is degraded.

## Can Haris integrate with a Security Operations Center or M-SOC workflow?

Yes. Haris is designed to support SOC and M-SOC style operations by forwarding structured telemetry, logs, and health context into centralized monitoring environments.
