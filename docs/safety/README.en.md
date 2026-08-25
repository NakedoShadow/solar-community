*[Version française](README.md)*

# Electrical safety — design constraint

## The rule

**Solar Community publishes no content that pushes someone to install an electrical system alone** (panels, wiring, inverter, battery or grid connection). This isn't excessive caution: a poorly done solar installation is a real fire and electrocution risk, and in most jurisdictions, grid connection is subject to rules (certification, professional inspection) this project has neither the legitimacy nor the competence to bypass.

This rule sits at the **same priority level** as BioSentinel's `sho-dataguard` privacy constraint: non-negotiable, with veto power held by the responsible operator (`sho-safeguard`) over any content or feature that violates it.

## What's in scope right now

- **Monitoring firmware** — reading production, battery charge, inverter state. None of this requires handling live current during install: it reads measurement points already present on certified hardware.
- **BOM generation** (`sho-kitbuilder`) — recommending components, with sources and prices. Recommending is not guiding an installation.
- **Site mapping** (`sho-fieldmapper`) — satellite imagery analysis, no physical handling.
- **Load balancing** (`sho-balancer`) — pure software, MQTT between already-installed nodes.
- **Software tutorials** (`sho-trainer`) — using the dashboard, configuring monitoring, reading your data. No wiring tutorial.

## What's explicitly out of scope for now

- Any step-by-step wiring, inverter/battery connection, or grid-connection guide.
- Any feature that would present a DIY installation as sufficient without validation by a qualified professional.

## What it would take to lift this limit someday

Before considering any content touching physical installation, at minimum:
1. Review by a qualified person (a certified electrician), not just the project team.
2. Explicit warnings and references to local codes, with a clear liability disclaimer — and probably country/region variants rather than one single guide.
3. A default that points toward a certified professional/installer rather than self-install, with self-install offered as a clearly marked option only where the local jurisdiction allows it.

Until those conditions are met, `sho-safeguard` blocks. That's a deliberate block, not an oversight.
