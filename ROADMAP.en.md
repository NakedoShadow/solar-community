*[Version française](ROADMAP.md)*

# Roadmap

Solar Community's technical milestones. Each version must be functional before the next. No milestone touching physical installation appears until `sho-safeguard` has validated the safety framework ([docs/safety/](docs/safety/README.en.md)).

## v0.1 — Core software tools
- [ ] Minimal BOM generator (`sho-kitbuilder`): component list for a given budget, with sources
- [ ] Site-mapping pipeline (`sho-fieldmapper`): annual sunlight via Sentinel-2 for a GPS point
- [ ] `sho-safeguard` review: confirm neither crosses the physical-installation line

## v0.2 — Monitoring
- [ ] Firmware reading production/battery/inverter, on a node already installed by a qualified third party
- [ ] Payload format reviewed by `sho-safeguard` and the `sho-dataguard`-equivalent (no household personal data)

## v0.3 — Real ingestion
- [ ] Node.js backend + MQTT broker
- [ ] TimescaleDB: time-series schema
- [ ] The v0.2 firmware sends to the real backend

## v0.4 — Minimal dashboard
- [ ] React + D3.js, one chart, customizable
- [ ] Public deployment, no-account access

## v0.5 — Real balancing
- [ ] `sho-balancer`: MQTT balancing daemon, tested on at least two simulated then real nodes

## v1.0 — First real pilot
- [ ] Deployment with qualified installers (no self-install)
- [ ] Real measurements of grid-dependency reduction — published only once measured, never anticipated
- [ ] First `sho-trainer`/dashboard report generated from real data

---

Nothing here is fixed: this document evolves with decisions made in issues/PRs.
