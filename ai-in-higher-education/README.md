# AI in Higher Education

### Student Perceptions of Course-Level AI Policies: Evidence from a Conjoint Experiment

![Status](https://img.shields.io/badge/status-working%20paper-orange)
![Method](https://img.shields.io/badge/method-conjoint%20experiment-blue)
![Sample](https://img.shields.io/badge/sample-358%20students-green)
![Language](https://img.shields.io/badge/code-R-lightgrey)

---

## Overview

This project examines how students evaluate different forms of artificial intelligence (AI) integration in university courses.

Rather than asking whether AI should be used in higher education, this study asks:

> **How should AI be used in higher education?**

Using a conjoint experiment, students evaluated hypothetical course policies that varied in:

- AI use in instructional materials
- AI use in assessments and grading
- AI-powered personalized support

The experiment identifies which policy designs increase or decrease:

- Perceived usefulness
- Support for adoption
- Perceived autonomy

---

## Main Finding

The central result is straightforward:

> Students are not opposed to AI itself.  
> Students are opposed to AI operating without human oversight.

AI-assisted systems that remained under instructor review received evaluations similar to traditional human-only approaches.
By contrast, AI systems operating without instructor review produced substantial declines in support, perceived usefulness, and autonomy.

---

## Research Design

### Conjoint Experiment

Participants evaluated randomly generated course policies composed of three dimensions:

| Attribute | Levels |
|------------|------------|
| Instructional Materials | No AI, AI reviewed by instructor, AI unreviewed |
| Assessments & Grading | Human grading, AI reviewed by instructor, AI unreviewed |
| Personalized Support | No chatbot, AI chatbot |

Each participant evaluated six randomly assigned profiles.

### Outcomes

Participants rated each profile on 0–100 scales:

1. Perceived usefulness
2. Support for adoption
3. Perceived autonomy

---

## Sample

- Undergraduate students
- N = 358 respondents
- 2,148 profile evaluations
- Online Qualtrics survey
- Fall 2025

---

# Key Results

## Human Oversight Matters

The largest negative effects occur when AI operates without instructor review.

![Human Oversight](figures/featured_higher_ed.png)

---

## Effects on Perceived Usefulness

Students strongly penalize unreviewed AI systems, especially when used for grading and instructional materials.

![Perceived Usefulness](figures/perceived_usefulness_amce.png)

---

## Effects on Support for Adoption

Support for AI adoption depends heavily on whether instructors remain involved in reviewing AI outputs.

![Support for Adoption](figures/support_amce.png)

---

## Effects on Perceived Autonomy

Students report lower autonomy when AI assumes responsibility for instructional or evaluative decisions without human oversight.

![Perceived Autonomy](figures/autonomy_amce.png)

---

## Comparative Effect Sizes

Coefficient estimates across all outcomes reveal a consistent pattern.

- AI without review produces large negative effects.
- AI with instructor review produces substantially smaller effects.
- Course chatbots have little impact.

![Coefficient Plot](figures/coefficient_plot.png)

---

# Repository Structure

```text
ai-in-higher-education/
│
├── README.md
│
├── analysis/
│   ├── ai_higher_ed_analysis.R
│   ├── data_cleaning.R
│   ├── models.R
│   └── visualizations.R
│
├── docs/
│   ├── conference_paper.pdf
│   ├── working_paper.pdf
│   └── appendices.pdf
│
├── materials/
│   ├── survey_instrument.pdf
│   ├── conjoint_profiles.pdf
│   ├── consent_form.pdf
│   └── experimental_materials.pdf
│
├── figures/
│   ├── featured_higher_ed.png
│   ├── perceived_usefulness_amce.png
│   ├── support_amce.png
│   ├── autonomy_amce.png
│   └── coefficient_plot.png
```

---

# Methods

The primary analyses use:

- Linear mixed-effects models
- Average Marginal Component Effects (AMCEs)
- Estimated marginal means

Main R packages:

```r
library(tidyverse)
library(lme4)
library(lmerTest)
library(emmeans)
library(broom.mixed)
library(ggplot2)
library(patchwork)
```

---

# Current Status

### Completed

- [x] Data collection
- [x] Data cleaning
- [x] Conjoint analysis
- [x] Conference paper
- [x] Main figures

### In Progress

- [ ] Journal manuscript
- [ ] Heterogeneity analyses
- [ ] AI literacy moderators
- [ ] Technology Acceptance Model (TAM) extensions
- [ ] Educational trust measures

---

# Key Contributions

This study contributes to the literature on artificial intelligence in education by:

1. Providing causal evidence on student evaluations of AI-enabled course policies.
2. Demonstrating that human oversight is a critical determinant of AI legitimacy in educational settings.
3. Distinguishing between instructional, evaluative, and support functions of AI.
4. Showing that students respond differently depending on where AI is integrated into learning process.

---

## License

This repository is released for academic and research purposes.
Data are not publicly available due to IRB and participant confidentiality requirements.
