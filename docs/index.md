# Haris Docs

<div class="hero-shell">
  <div class="hero-kicker">Platform documentation</div>
  <h1>Haris Docs</h1>
  <p>
    Haris is a vessel-edge platform for maritime telemetry collection,
    onboard normalization, health monitoring, and secure integration with
    Maritime Security Operations Center workflows.
  </p>
</div>

---

## <span class="section-label">Overview</span> Documentation for operators and implementers

This site presents Haris as a documentation-first platform reference. It is intended for operators, engineers, and reviewers who need a clear understanding of the system architecture, deployment sequence, and security posture before field use.

<hr class="glow-divider">

## <span class="section-label">Capabilities</span> Core platform functions

<div class="feature-grid">
  <div class="feature-card">
    <h3>Collection</h3>
    <p>Collects vessel telemetry from NMEA 0183, NMEA 2000, and Signal K compatible sources in an edge-first operating model.</p>
  </div>
  <div class="feature-card">
    <h3>Processing</h3>
    <p>Parses, normalizes, and buffers data onboard so collection remains effective even when connectivity is unstable or intermittent.</p>
  </div>
  <div class="feature-card">
    <h3>Operations</h3>
    <p>Uses Watchtower automation to provision service state, storage, connectivity, telemetry freshness, and core-side observability.</p>
  </div>
  <div class="feature-card">
    <h3>Security</h3>
    <p>Applies encrypted transport, fail-closed assumptions, restricted services, and deployment controls as part of a layered security posture.</p>
  </div>
</div>

## <span class="section-label">Operational Model</span> Why edge-first matters

- Processes and normalizes data on the vessel instead of depending on continuous upstream availability.
- Buffers locally so the node remains functional during unstable or intermittent links.
- Forwards structured telemetry, logs, and health context into SOC and M-SOC workflows.
- Establishes a cleaner trust boundary before data reaches central infrastructure.
- Applies repeatable vessel-edge and M-SOC configuration through Watchtower playbooks.

<div class="cta-panel">
  <p><strong>Recommended reading path:</strong> review the architecture, Watchtower, deployment, and security pages in sequence before preparing a vessel installation or core-side integration.</p>
</div>
