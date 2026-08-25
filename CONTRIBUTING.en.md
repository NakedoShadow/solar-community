*[Version française](CONTRIBUTING.md)*

# Contributing to Solar Community

The project is young (see [ROADMAP.md](ROADMAP.en.md)). Read the [WHITEPAPER.md](WHITEPAPER.en.md) and [docs/safety/](docs/safety/README.en.md) first — the electrical safety constraint is non-negotiable and governs what can or cannot enter this repository.

## How to contribute

1. Fork, create a descriptive branch (`bom/panel-catalog`, `siting/sentinel2-pipeline`, etc.).
2. Open an issue before a large PR if the change touches the architecture.
3. Commit small and clear.
4. Describe the *why* in the PR, not just the *what*.

## Absolute rule: any PR touching physical installation goes through `sho-safeguard`

Any contribution that, even indirectly, points toward installation, wiring, or electrical connection must be explicitly reviewed for safety before merge (see [docs/safety/](docs/safety/README.en.md)). Until the SHO operators are activated, this review is done manually by the maintainer, with the same rigor. When in doubt, the PR is rejected by default — it's not the PR author's job to prove it's safe, the burden of proof runs the other way.

## Proposing a hardware component

`sho-kitbuilder` format: a note in `firmware/notes/` or `bom/`, with datasheet link, price/availability, why this choice, known limitations.

## Proposing a site or mapping method

`sho-fieldmapper` format: document the data source (Sentinel-2 or equivalent free source), the evaluation method, and precision limits.

## Code style

Not yet fixed — the first software tools (v0.1, see [ROADMAP.md](ROADMAP.en.md)) will set the conventions.

## Reporting an issue

- **Technical bug** → *Bug report* template.
- **Component proposal** → *Component proposal* template.
- **Electrical safety concern** → *Safety concern* template, treated as absolute priority.

## License of your contributions

Any contribution is submitted under the project's [MIT](LICENSE) license.
