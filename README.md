# Carbon-Dioxide-Capture: CO₂ Capture Recommender

A browser-based screening tool that suggests the best-fit CO₂ capture technology and material for a given gas condition.

**Live tool:** https://mujtabaansari-1709.github.io/Carbon-Dioxide-Capture/

> **Disclaimer:** This is a first-pass screening aid, not a design basis. Validate any result with process simulation or experimental data before relying on it.

## What it does

Enter your conditions and the tool returns:

- the best technology (amine absorption, chilled ammonia, physical solvents, membranes, solid sorbents, cryogenic, oxy-fuel, calcium looping, direct air capture)
- the best material or solvent for that technology
- a ranked list of all technologies and materials, with warnings for poor fits
- the reported literature evidence (cost and energy figures) where available

### Inputs

| Input | Notes |
|---|---|
| Source / capture route | Coal flue gas, natural-gas flue gas, cement kiln, syngas, oxy-fuel, natural gas / biogas processing, ambient air |
| CO₂ concentration (vol %) | Used with total pressure to compute CO₂ partial pressure |
| Total pressure (bar abs) | |
| Gas temperature (°C) | |
| Capture scale (t CO₂/day) | |
| Contaminants | Clean, SO₂/NOₓ/O₂, or H₂S |
| Gas moisture | Humid or dry |
| Product purity | Standard (>95%) or very high (>99.5%) |

## How it works

Each technology and material is scored against operating windows for CO₂ partial pressure, temperature and scale, with adjustments for contaminants, moisture and purity. About 80% of the score comes from these engineering rules and about 20% from how often each technology appears for the same capture route in a CCS project registry.

## Evidence status

- The project registry (Jan 2023, 417 projects) has no temperature, pressure or material data, so it only supplies the technology-usage prior.
- Source gas presets (coal ~13%, natural gas ~4%, cement ~15%, syngas ~35% CO₂) and the membrane, sorbent and direct-air-capture figures come from a first literature pass. Most of those sources are not ScienceDirect open-access papers.
- Cost figures use different years and currencies, so they are displayed as evidence only and do not affect the ranking.

## Planned improvements

- Replace the rules with a model fitted to measured data: adsorption isotherms (NIST/ARPA-E adsorbent database), membrane permeability and selectivity (Polymer Gas Separation Membrane Database), and solvent and cost data from open-access review papers.
- Add cost-based ranking with all figures converted to a common currency and year.
- Add a citation for every number in the tool.

## Usage

Open `index.html` in any browser, or use the live link above. There is nothing to install.
