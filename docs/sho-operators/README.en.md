*[Version française](README.md)*

# Shadow Hermes Operators (SHO)

Same model as [BioSentinel](https://github.com/NakedoShadow/biosentinel/blob/master/docs/sho-operators/README.en.md): each **SHO** is an isolated [Hermes](https://github.com/NousResearch/Hermes-Agent) profile in Bot Mode, with a precise role and scope. Solar Community introduces a fifth one compared to BioSentinel: `sho-safeguard`, because this project touches a physical risk (electricity) that BioSentinel didn't have.

## The five operators

### `sho-kitbuilder`
**Role:** compile open-source component lists (panels, controllers, batteries) and generate BOMs (Bills of Materials) sized to different budgets.
**Scope:** recommendation with sources, no installation instructions. Output in `bom/`.

### `sho-fieldmapper`
**Role:** use GPS data and free satellite imagery (Sentinel-2) to identify optimal sites — annual sunlight, environmental impact.
**Scope:** site analysis and recommendation, no field action. Output in `siting/`.

### `sho-trainer`
**Role:** create tutorials and workshops so each participant can use the software (dashboard, monitoring, BOM generation) independently.
**Scope:** software pedagogy only. **No wiring or electrical-installation tutorial** until `sho-safeguard` has validated a framework (see [docs/safety/](../safety/README.en.md)).

### `sho-balancer`
**Role:** balance energy distribution across network nodes, via the open-source MQTT protocol, continuously.
**Scope:** pure software, operates on nodes already installed and connected by qualified third parties.

### `sho-safeguard`
**Role:** electrical and regulatory safety gatekeeper. Audits any content or feature that touches, even indirectly, the physical installation of an electrical system.
**Scope:** review, veto power — same standing as BioSentinel's `sho-dataguard`, but for physical safety rather than privacy. A `sho-safeguard` rejection blocks a merge, full stop.

## Status

Bootstrap: all five profiles exist, have a defined role (`SOUL.md`), wired to DeepSeek (`deepseek-v4-flash`) like the rest of Hermes. **Not yet activated** — same credit constraint as BioSentinel, reactivation after top-up.
