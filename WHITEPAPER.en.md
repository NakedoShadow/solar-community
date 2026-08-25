*[Version française](WHITEPAPER.md)*

# Solar Community — Whitepaper

**Version 0.1 — August 26, 2026**

---

## Abstract

Solar Community is an open-source framework for designing, sizing, and monitoring community solar micro-grids, independent of centralized energy providers. It rests on four principles: **decentralization** (autonomous but interconnected micro-grids), **transparency** (code, schematics, and protocols published under the MIT license), **extensibility** (modular hardware, DIY accepted at the software level), and **co-creation** (each community customizes its own dashboard). The project began as an intention formulated by ADA, an open-source agentic intelligence interface, directly following [BioSentinel](https://github.com/NakedoShadow/biosentinel).

This document complements [README.md](README.en.md) (quick start), [ROADMAP.md](ROADMAP.en.md) (milestones), and [CONTRIBUTING.md](CONTRIBUTING.en.md) (how to get involved).

## 1. The problem

Access to solar energy remains, in many communities, mediated by actors who impose their own rules: proprietary hardware, opaque buy-back rates, dependency on a single provider for both sizing and maintenance. A community that simply wants to produce and share its energy locally often lacks the tools to do so with full understanding — how many panels, where to place them, how to balance load between households.

## 2. Why open source, and why MIT

Same refusal of proprietary dependency as every project ADA initiates: code, electrical schematics, and communication protocols are public and auditable from the first commit. The license choice differs from BioSentinel (GPL-v3), though: Solar Community adopts the **MIT** license, more permissive. This is deliberate — a sizing-and-monitoring framework spreads faster if installers, local cooperatives, or hardware manufacturers can adopt it as-is, including in commercial offerings, without an obligation to open-source their own additions. The core project's transparency is guaranteed by publication itself, not by license constraint.

## 3. Founding principles

- **Decentralization** — each micro-grid operates autonomously while staying interconnected to share surplus energy with neighbors.
- **Transparency** — code, electrical schematics, and communication protocols published and open to review by anyone.
- **Extensibility** — the system accepts battery sensors, DIY inverters, and thermal storage solutions, with no fixed architecture.
- **Co-creation** — local communities customize their own dashboard, with visualizations reflecting their own priorities (carbon footprint reduction, food autonomy, etc.).

## 4. Technical architecture

| Pillar | Tech | Role |
|---|---|---|
| Monitoring firmware (`firmware/`) | Arduino-compatible | Reads production/battery/inverter |
| BOM generation (`bom/`) | Scripts / open data | Component lists by budget |
| Site mapping (`siting/`) | Sentinel-2 imagery | Sunlight/impact assessment |
| Data platform (`backend/`) | Node.js + MQTT + TimescaleDB | Ingestion, load balancing |
| Dashboard (`dashboard/`) | React + D3.js | Customizable visualization |

### Data flow

```
[Node installed — panels + inverter + battery, by qualified third parties]
   │ telemetry (production, charge, state) via MQTT
   ▼
[Node.js backend] ──► [TimescaleDB]
   │
   ├──► [sho-balancer] — adjusts distribution across nodes, hourly
   ▼
[React/D3 dashboard — customizable per community]
```

Firmware and backend only *measure* and *balance* an already-installed system — never guide its installation (section 6).

## 5. Governance: human, ADA, and the SHO operators

Same three-tier model as BioSentinel: the human maintainer decides and holds final responsibility, ADA delegates rather than building everything herself, and five **Shadow Hermes Operators (SHO)** — Hermes agents in Bot Mode — each own an isolated role: `sho-kitbuilder` (components), `sho-fieldmapper` (sites), `sho-trainer` (software pedagogy), `sho-balancer` (MQTT balancing), and `sho-safeguard` (electrical/regulatory safety gatekeeper, veto power). Details: [docs/sho-operators/](docs/sho-operators/README.en.md).

## 6. Electrical safety: the constraint that overrides everything else

Solar Community touches a risk BioSentinel didn't have: electricity. A poorly done solar installation is a real fire and electrocution risk, and grid connection is regulated by law in most jurisdictions. **This project will therefore not publish any guide pushing someone to install an electrical system alone.** Monitoring firmware (reading measurements on hardware already installed by professionals) is in scope; wiring and connection are not, until a safety framework has been validated — at minimum a review by a certified electrician, warnings compliant with local codes, and a default that points toward a professional rather than self-install. Full detail: [docs/safety/](docs/safety/README.en.md).

## 7. A note on this document's origin

The project's original seed (ADA's Dream Memory from August 24, 2026) describes a first pilot deployed in a fictional village, with precise energy- and CO₂-reduction figures. **That pilot never happened.** This whitepaper picks up the seed's vision and principles, but treats its deployment figures as targets to reach and validate under real conditions (see [ROADMAP.md](ROADMAP.en.md)), never as an already-achieved result.

## 8. Roadmap

Summary — full detail in [ROADMAP.md](ROADMAP.en.md):

- **v0.1** — Minimal BOM generator + site-mapping pipeline (Sentinel-2, one GPS point).
- **v0.2** — Monitoring firmware (reads production/battery) on a node already installed by a qualified third party.
- **v0.3** — MQTT + TimescaleDB backend, real ingestion.
- **v0.4** — Minimal, customizable dashboard.
- **v0.5** — `sho-balancer`: real balancing across at least two nodes.
- **v1.0** — First real pilot, measured (not assumed) figures on grid-dependency reduction.

## 9. How to contribute

See [CONTRIBUTING.md](CONTRIBUTING.en.md). Any proposal touching, even indirectly, physical installation goes through a `sho-safeguard` review before merge — no exceptions.

## 10. License

[MIT](LICENSE) — redistribution, modification, and commercial use permitted, including in closed offerings built on top.

---

*This document will evolve with the project.*
