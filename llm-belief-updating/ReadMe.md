# LLM Belief Updating

Experimental evidence on how accurate and deceptive AI explanations shape belief updating and factual reasoning.

![Status](https://img.shields.io/badge/status-active_research-darkgreen)
![Methods](https://img.shields.io/badge/methods-experimental_design-blue)
![Focus](https://img.shields.io/badge/focus-LLM_belief_updating-purple)



![Movement Toward Factual Accuracy](figures/issue_type_effects.png)

---

## Overview

This project investigates how LLM explanations influence human belief updating. Specifically, it examines whether AI-generated explanations reinforce or challenge preexisting beliefs when individuals evaluate factual, controversial, and politically relevant claims. As generative AI systems increasingly become intermediaries for scientific, political, and social information, understanding how people respond to AI-generated explanations is critically important. This project studies whether deceptive AI explanations move beliefs away from factual accuracy more effectively than accurate AI explanations move beliefs toward it. The study combines experimental survey methods with mixed-effects modeling to analyze how participants revise beliefs after exposure to AI-generated explanations.

---

## Research Questions

This project examines several interrelated questions:

- Do AI-generated explanations influence belief updating?
- Are deceptive AI explanations more persuasive than accurate AI explanations?
- Are individuals more likely to accept AI explanations that align with their prior beliefs?
- Does motivated reasoning constrain AI-driven belief change?
- Are controversial beliefs more resistant to correction than factual or trivia-based beliefs?
- Does self-rated knowledge moderate susceptibility to deceptive AI explanations?

---

## Experimental Design

Participants evaluate a series of factual and controversial statements before and after exposure to AI-generated explanations.

### Experimental Conditions

| Condition | Description |
|---|---|
| Accurate AI Explanation | AI provides factually correct explanatory feedback |
| Deceptive AI Explanation | AI provides misleading or factually incorrect explanatory feedback |

### Statement Types

| Type | Examples |
|---|---|
| Controversial / belief-relevant | Election integrity, vaccines, climate change, immigration |
| Factual / trivia-based | Great Wall visibility, boiling point of water, lightning myths |

### Procedure

For each statement, participants:

1. rate how true they believe the statement is
2. receive an AI-generated explanation
3. re-rate the statement after exposure
4. report how knowledgeable they are about the topic

The project uses:
- within-subject manipulation of AI explanation accuracy
- between-subject comparison of issue types
- repeated belief updating measurements

---

## Key Findings

Preliminary analyses suggest several important patterns:

- Accurate AI explanations produce modest movement toward factual accuracy.
- Deceptive AI explanations produce substantially larger movement away from factual accuracy.
- Participants appear more resistant to belief updating on controversial issues than on factual/trivia statements.
- Self-rated knowledge moderates susceptibility to deceptive AI explanations.
- AI explanations systematically shape belief updating across multiple domains.

These findings suggest that generative AI systems may possess asymmetric persuasive effects, where misleading explanations exert stronger influence than corrective ones.

---

## Methods

### Analytical Approach

- Experimental survey design
- Mixed-effects regression modeling
- Random intercepts for participants and statements
- Interaction modeling for knowledge and issue type effects

### Statistical Tools

- R
- tidyverse
- lme4
- lmerTest
- ggeffects
- ggplot2
- emmeans

---

## Repository Structure

```text
llm-belief-updating/
│
├── README.md
├── analysis/
├── figures/
├── materials/
├── docs/
└── .gitignore
```

### Folder Descriptions

| Folder | Description |
|---|---|
| `analysis/` | Quarto and R analysis scripts |
| `figures/` | Generated visualizations and plots |
| `materials/` | Experimental materials and survey instruments |
| `docs/` | Draft papers, appendices, and supporting documents |

---
## Research Areas

- Human-AI Interaction
- Computational Social Science
- AI Persuasion
- Misinformation Studies
- AI Governance
- Experimental Methods

---

## Project Status

This project is currently under active development. Analyses, figures, and experimental materials may continue to evolve as the research progresses.
