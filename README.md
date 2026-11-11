# Claude BRENDA Database Skill

A Python-oriented skill for querying the BRENDA enzyme database through its SOAP API. It supports biochemical research workflows involving enzyme kinetics, reactions, substrate specificity, organism comparisons, environmental conditions, and enzyme discovery.

## What It Covers

- **Kinetic parameters:** Retrieve Km, kcat, and related enzyme data.
- **Reaction information:** Find reaction equations, substrates, products, and organism-specific details.
- **Enzyme discovery:** Search for enzymes by substrate, product, EC number, or reaction pattern.
- **Organism comparisons:** Compare enzyme characteristics across selected organisms.
- **Environmental conditions:** Explore pH, temperature, stability, and cofactor requirements.
- **Substrate specificity:** Analyze affinity and kinetic measurements across substrates.
- **Regulation:** Retrieve inhibitor and activator information.
- **Engineering workflows:** Identify candidate variants and assemble enzyme pathway analyses.
- **Visualization:** Generate kinetic, organism-comparison, pH, and temperature plots.

## Installation

Clone the repository into your Claude skills directory:

```bash
git clone https://github.com/Brajesh31/claude-brenda-database-skill.git ~/.claude/skills/brenda-database
```

Install the Python dependencies:

```bash
uv pip install zeep requests pandas matplotlib seaborn
```

## Authentication

BRENDA API access requires account credentials. Configure them through environment variables or a local `.env` file:

```env
BRENDA_EMAIL=your.email@example.com
BRENDA_PASSWORD=your_brenda_password
```

Do not commit credentials or share them in prompts. Confirm that your BRENDA account has the required API access.

## Using the Skill

Example request:

```text
Use the brenda-database skill to retrieve Km values for EC 1.1.1.1,
filter by organism and substrate, and compare the available measurements.
```

Other supported workflows include reaction lookup, enzyme discovery for a substrate, cross-organism comparisons, pH and temperature analysis, inhibitor lookup, and kinetic-model preparation.

## Helper Scripts

- `scripts/brenda_queries.py` provides query, parsing, comparison, and extraction helpers.
- `scripts/brenda_visualization.py` provides enzyme-data plots.
- `scripts/enzyme_pathway_builder.py` supports pathway and retrosynthesis workflows.

See [SKILL.md](SKILL.md) for function examples, data formats, workflows, and troubleshooting.

## Good Practices

Validate EC numbers and parsed values, handle incomplete records, cache repeated queries, and observe the service's usage limits. Kinetic values depend on experimental conditions and source literature, so preserve organism, substrate, pH, temperature, and citation context when comparing results.

## License

See [LICENSE](LICENSE) for the repository license.
