# Data and Materials for Epistemically Double-Edged

## Overview

This repository contains the de-identified data and analysis materials supporting the manuscript *Epistemically Double-Edged: How Accurate and Deceptive AI Explanations Shape Factual Beliefs* by Namig Abbasov.

The study examined how accurate and deceptive AI-generated explanations affect factual belief updating. In a within-subjects survey experiment, 358 university students evaluated eight factual statements. For each statement, participants rated its truth, viewed either an accurate or deceptive AI-generated explanation, rated the statement again, and reported their perceived knowledge of the topic. The analytic dataset contains 2,864 participant-by-statement trials.

## Files

### `epistemically_double_edged_participants.csv`

Participant-level data with one row per participant and 358 rows in total. This file contains the original item responses and calculated measures used for generalized AI trust, critical evaluation of AI information, objective AI literacy, and the exploratory political-ideology analysis.

### `epistemically_double_edged_trials.csv`

Long-format trial-level data with one row per participant-by-statement trial and 2,864 rows in total. Each participant contributes eight rows, one for each factual statement. This file contains explanation condition, statement characteristics, pre- and post-explanation belief ratings, topic knowledge, and truth-aligned belief-accuracy outcomes.

### `llm_belief_updating.qmd`

Quarto/R analysis code used to construct the analytic variables, estimate the statistical models, conduct robustness checks, and generate the reported tables and figures.

### `Survey Instrument_Respondent Version.docx`

Respondent-facing survey instrument, including the question wording, response scales, factual statements, accurate and deceptive explanations, and debriefing information.

## Study Design

- Design: within-subjects survey experiment
- Participants: 358
- Trials per participant: 8
- Total trial-level observations: 2,864
- Explanation conditions: accurate and deceptive
- Statement contexts: four controversial and four neutral statements
- Truth status: four true and four false statements
- Assignment: explanation condition randomized across statements
- Primary outcome: change in truth-aligned factual-belief accuracy

Every participant evaluated all eight statements and encountered both explanation conditions. For each statement, a participant saw only one explanation version.

## Data Linkage

The variable `participant_id` is a paper-specific pseudonymous identifier. It connects each participant's row in the participant-level file to the same participant's eight rows in the trial-level file. Original Qualtrics response identifiers and the mapping between original and public identifiers are not included.

## Participant-Level Variables

| Variable | Description | Coding |
| --- | --- | --- |
| `participant_id` | Paper-specific pseudonymous participant identifier | Character identifier |
| `trust_item_1` | AI is capable and knowledgeable in its domain | 1–7; higher values indicate stronger agreement |
| `trust_item_2` | AI performs its tasks effectively | 1–7 |
| `trust_item_3` | AI acts in the participant's best interest | 1–7 |
| `trust_item_4` | AI is concerned about the participant's well-being | 1–7 |
| `trust_item_5` | AI is honest and keeps its promises | 1–7 |
| `trust_item_6` | AI adheres to principles the participant considers acceptable | 1–7 |
| `trust_ai` | Mean of the six generalized AI-trust items | 1–7; at least four valid items required |
| `critical_evaluation` | Likelihood of critically evaluating information received from an AI tool | 1–7; higher values indicate greater reported critical evaluation |
| `literacy_item_1_response` | Original response to the definition-of-AI item | Response option recorded in the survey |
| `literacy_item_2_response` | Original response to the AI-output-generation item | Response option recorded in the survey |
| `literacy_item_3_response` | Original response to the LLM-understanding item | Response option recorded in the survey |
| `literacy_item_4_response` | Original response to the LLM-limitations item | Response option recorded in the survey |
| `literacy_item_1_correct` | Correctness of literacy item 1 | 1 = correct; 0 = incorrect; blank = missing |
| `literacy_item_2_correct` | Correctness of literacy item 2 | 1 = correct; 0 = incorrect; blank = missing |
| `literacy_item_3_correct` | Correctness of literacy item 3 | 1 = correct; 0 = incorrect; blank = missing |
| `literacy_item_4_correct` | Correctness of literacy item 4 | 1 = correct; 0 = incorrect; blank = missing |
| `ai_literacy_proportion` | Proportion of valid literacy items answered correctly | 0–1; at least three valid items required |
| `political_ideology` | Liberal-conservative self-placement used in the exploratory analysis | 1 = most liberal; 10 = most conservative |

The six generalized AI-trust items use a seven-point agreement scale from *Strongly Disagree* to *Strongly Agree*. The critical-evaluation item uses a seven-point likelihood scale from *Very Unlikely* to *Very Likely*.

## Trial-Level Variables

| Variable | Description | Coding |
| --- | --- | --- |
| `participant_id` | Pseudonymous participant identifier | Matches the participant-level file |
| `statement_id` | Identifier for the factual statement | Eight named statement categories |
| `issue_context` | Substantive context of the statement | `controversial` or `neutral` |
| `statement_true` | Objective truth status of the statement | `TRUE` or `FALSE` |
| `explanation_condition` | Randomly assigned explanation type | `accurate` or `deceptive` |
| `pre_belief_rating` | Belief rating before the AI explanation | 1 = Definitely False; 7 = Definitely True |
| `post_belief_rating` | Belief rating after the AI explanation | 1 = Definitely False; 7 = Definitely True |
| `topic_knowledge` | Self-rated knowledge after the explanation | 1 = Not at all knowledgeable; 7 = Extremely knowledgeable |
| `pre_truth_aligned_accuracy` | Pre-explanation rating recoded toward objective truth | 1–7; higher values indicate greater factual accuracy |
| `post_truth_aligned_accuracy` | Post-explanation rating recoded toward objective truth | 1–7; higher values indicate greater factual accuracy |
| `accuracy_change` | Change in truth-aligned accuracy | Post accuracy minus pre accuracy; positive values indicate movement toward truth |

## Factual Statements

| `statement_id` | Statement | Truth status | Context |
| --- | --- | --- | --- |
| `election` | The 2020 U.S. presidential election was secure and free from widespread fraud. | True | Controversial |
| `vaccines` | Vaccines cause more harm than the diseases they are meant to prevent. | False | Controversial |
| `climate` | Human activity is the primary cause of climate change. | True | Controversial |
| `gun_control` | Gun control laws lead to increased violent crime. | False | Controversial |
| `great_wall` | The Great Wall of China is visible from space with the naked eye. | False | Neutral |
| `water_boil` | Water boils at 100°C (212°F) at sea level. | True | Neutral |
| `bones` | The human body has 206 bones. | True | Neutral |
| `lightning` | Lightning never strikes the same place twice. | False | Neutral |

The complete accurate and deceptive explanation texts are provided in the survey instrument and manuscript appendix.

## Construction of Truth-Aligned Outcomes

Original belief ratings range from 1 (*Definitely False*) to 7 (*Definitely True*). For objectively true statements, the original rating is retained. For objectively false statements, accuracy is calculated as `8 - original rating`. The resulting pre- and post-explanation accuracy measures therefore range from 1 to 7, with higher values consistently indicating greater factual accuracy.

The primary outcome is calculated as:

```text
accuracy_change = post_truth_aligned_accuracy - pre_truth_aligned_accuracy
```

Positive values indicate movement toward factual truth, negative values indicate movement away from truth, and zero indicates no change.

## Missing Values

Missing values are represented by blank cells in the CSV files. The primary trial dataset requires nonmissing pre- and post-explanation ratings. Topic knowledge may be missing because it was not used to determine whether a trial was valid. The generalized AI-trust score requires at least four valid responses across six items. The objective AI-literacy score requires at least three valid responses across four items.

## Privacy and De-identification

The public files exclude names, email addresses, IP addresses, geographic coordinates, timestamps, Qualtrics response identifiers, recruitment-system identifiers, consent records, free-text demographic responses, unused demographic variables, party identification, and variables from the separate course-policy experiment. The public participant identifiers are specific to this paper, and no re-identification key is provided.

The deposited files should not be combined with private or administrative records in an attempt to identify participants.

## Reproducing the Analysis

The analysis was conducted in R. See `llm_belief_updating.qmd` for package requirements, variable construction, model specifications, robustness checks, tables, and figures.

The public CSV files contain uncentered scale scores. Centered and standardized variables used in the statistical models should be reconstructed in the analysis code from these original measures.

## Citation

Please cite the archived dataset using the complete citation displayed on the Zenodo record after publication. The record citation will identify Namig Abbasov as creator and include the version-specific DOI.

## License

Reuse is governed by the license displayed on the Zenodo record. The selected license must be consistent with the study's consent terms, ethics determination, and institutional requirements.

## Contact

Namig Abbasov  
AI & Technology Initiatives Librarian  
Stanford Law School  
namig.abbasov@stanford.edu
