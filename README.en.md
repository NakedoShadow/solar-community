*[Version française](README.md)*

<p align="center"><img src="docs/brand/social-preview.png" alt="Solar Community" width="800"></p>

# Solar Community

> An open-source framework for designing, sizing, and monitoring community solar micro-grids — without depending on centralized energy providers.

📄 [Whitepaper](WHITEPAPER.en.md) · 🗺️ [Roadmap](ROADMAP.en.md) · 🤝 [Contributing](CONTRIBUTING.en.md) · 🛡️ [Security (code)](SECURITY.md) · ⚡ [Electrical safety](docs/safety/README.en.md) · 💬 [Code of Conduct](CODE_OF_CONDUCT.en.md)

## Origin

Solar Community began as a seed in [ADA](https://nakedo.wordpress.com/)'s [Dream Memory](https://nakedo.wordpress.com/2026/08/24/eclairer-lavenir-deployer-un-reseau-solaire-communautaire-open-source/) on August 24, 2026, right after [BioSentinel](https://github.com/NakedoShadow/biosentinel). The original seed even describes a first pilot deployed in a fictional village ("Saint-Loup-sur-Mér") with precise energy- and CO₂-reduction figures — **that pilot does not exist**. It's a vision projected by the Dream Memory, not a real deployment. This repository picks up that vision as a starting point, not as an achieved result (see the [roadmap](ROADMAP.en.md) for what's actually planned, and on what timeline).

**Current status: bootstrap.** Nothing is deployed in the field yet.

## Why open source, and why MIT (not GPL like BioSentinel)

Same refusal of proprietary dependency as everywhere else in ADA's work: code, schematics, and protocols are public from the first commit, with no financial barrier to auditing, adapting, or redeploying. The license chosen here is **MIT**, deliberately more permissive than BioSentinel's GPL-v3: a sizing-and-monitoring framework is more likely to spread fast if installers, cooperatives, or hardware manufacturers can integrate it as-is — including into products they sell — without an obligation to open-source their own additions on top. The core project's transparency stays guaranteed; what changes is that no one is forced to open what they build on top of it.

## Non-negotiable design constraint: electrical safety first

**This repository will not publish any guide that pushes someone to DIY an electrical installation alone.** Monitoring firmware (reading production, battery charge, inverter state) is in scope; the physical installation of panels, wiring, and inverters is not, until a safety framework is defined and validated. Details and status: [docs/safety/](docs/safety/README.en.md).

## Intended architecture

| Pillar | Tech | Role |
|---|---|---|
| **Monitoring firmware** (`firmware/`) | Arduino-compatible | Reads production/battery/inverter — no install guide |
| **BOM generation** (`bom/`) | Scripts / open data | Component lists sized to a budget (`sho-kitbuilder`) |
| **Site mapping** (`siting/`) | Free Sentinel-2 imagery | Evaluates sunlight and impact of a site (`sho-fieldmapper`) |
| **Data platform** (`backend/`) | Node.js + MQTT + TimescaleDB | Ingests measurements, balances load (`sho-balancer`) |
| **Dashboard** (`dashboard/`) | React + D3.js | Visualization each community can customize |

## The SHO operators

Same as BioSentinel: development is orchestrated by **Shadow Hermes Operators** — isolated Hermes profiles in Bot Mode, one role each. Details: [docs/sho-operators/README.en.md](docs/sho-operators/README.en.md).

| Operator | Role |
|---|---|
| `sho-kitbuilder` | Generates BOMs (component lists) sized to a budget |
| `sho-fieldmapper` | Identifies optimal sites via free satellite imagery |
| `sho-trainer` | Tutorials and workshops — software usage, not electrical installation |
| `sho-balancer` | Load balancing across nodes via MQTT |
| `sho-safeguard` | Electrical/regulatory safety gatekeeper — veto power, same role as BioSentinel's `sho-dataguard` |

## Contributing

Full process, proposal format, and the safety-review rule: [CONTRIBUTING.en.md](CONTRIBUTING.en.md).

## License

[MIT](LICENSE)
