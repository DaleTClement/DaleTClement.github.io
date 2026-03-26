---
layout: page
title: "How Movement Decisions Shape Disease Spread"
permalink: /research/simple-trips/
---

## The Question

When an epidemic is spreading, people change how they move. They might stay home more, avoid crowded places, or shift their travel to locations that seem safer. Public health messaging generally assumes these precautions help. **But what happens when people's perception of risk doesn't match how the disease actually spreads?**

## The Model

We built a compartmental disease model (**SIS**) where individuals make day trips between a home location and two away locations that differ in their disease transmission rates. Individuals adjust their travel behavior based on one of three **risk proxies** — imperfect signals they use to estimate danger:

- **Prevalence** — how many infected individuals are nearby
- **Density** — how crowded a location is
- **Place** — inherent features of a location (e.g., ventilation, sanitation)

We studied two types of behavioral response:

- **Absolute** — reduce total travel (stay home more)
- **Relative** — redistribute trips toward locations perceived as safer

And two modes of disease transmission:

- **Density-dependent** — transmission scales with the number of contacts (more people = more infection)
- **Frequency-dependent** — transmission depends on the *fraction* of people who are infected, regardless of crowd size

<div style="text-align: center; margin: 30px 0;">
  <img src="/assets/images/simple-trips-schematic.svg" alt="Simple Trips model schematic: home location connected to two away locations with different transmission rates" style="max-width: 500px; width: 100%;">
  <p style="color: #666; font-size: 13px; margin-top: 8px;">Individuals make day trips from home to two away locations. They adjust travel based on perceived risk.</p>
</div>

## Key Findings

**Staying home more (absolute response) consistently reduces disease.** Regardless of which risk proxy people use or how the disease transmits, reducing total travel lowers infection rates.

**Shifting travel (relative response) can backfire.** When individuals redistribute their trips to locations that *seem* safer — but use a risk signal that doesn't match the actual transmission mode — disease prevalence can *increase* compared to doing nothing:

- Under **density-dependent** transmission, using **place-based** perception can be harmful
- Under **frequency-dependent** transmission, using **density-based** perception can be harmful

These "detrimental response" regions arise because the risk proxy systematically misdirects movement, concentrating people in locations that are actually more dangerous.

**The best risk proxy depends on the disease.** Prevalence-based perception is the most robust across scenarios. Density and place-based perception can be effective — but only when matched to the right transmission mode.

## Interactive Results Explorer

Use the app below to explore how different combinations of transmission mode, risk proxy, and behavioral response affect disease outcomes. Toggle between parameter sweeps to see when and why cautious behavior can backfire.

<div style="border: 1px solid #ddd; border-radius: 8px; overflow: hidden; margin: 20px 0; box-shadow: 0 2px 8px rgba(0,0,0,0.1);">
  <iframe
    src="https://daletclement.shinyapps.io/simple-trips-app/"
    width="100%"
    height="650"
    style="border: none;"
    loading="lazy"
    title="Simple Trips Interactive Results Explorer">
  </iframe>
</div>
<p style="color: #888; font-size: 12px; text-align: center;">
  If the app doesn't load, <a href="https://daletclement.shinyapps.io/simple-trips-app/" target="_blank" rel="noopener noreferrer">open it in a new tab</a>.
</p>

## Technical Details

- **Model**: SIS compartmental model with Simple Trips movement kernel (Ruktanonchai et al., 2016)
- **Implementation**: Solved as an ODE system with adaptive behavioral feedback
- **Parameter sweeps**: R₀, movement rate, pre-disease density distribution, transmission variance, response strength
- **Code**: R (model + analysis), Shiny (interactive figures), Python (independent replication)
- **All results are pre-computed** from >74,000 parameter combinations

## Manuscript

D.T. Clement, R.D. Holt, N.W. Ruktanonchai, O. Saucedo, N.A. Kortessis. *In Review.* Host behavioral responses to perceived risk shape spatial disease dynamics. *Population Biology Modeling and Theory.*
