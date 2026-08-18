# AIRBDS Core: AI-Readiness Dataset Scoring Metric

A structured, machine-readable checklist for evaluating how ready a bioscience
dataset is for AI and machine-learning use.

Maintained by the AI-Ready Bioscience Datasets Working Group
([AIRBDS](https://aibio.ac.uk/about/working-groups/airbds/)), AIBIO-UK.

**Current version: 1.0.1** — [`airbds_metric.json`](airbds_metric.json)

See preprint article for more information: <a href="https://doi.org/10.5281/zenodo.21803891"><img width="191" height="20" alt="image" src="https://github.com/user-attachments/assets/5fb6c700-fa37-4f8a-b0c2-b494be59180e" /></a>

---

## Purpose

The AIRBDS working group, part of [AIBIO-UK](https://aibio.ac.uk/),
was setup to create a catalogue of AI-ready bioscience datasets. The first 
crucial step in that process is constructing a clear definition of AI readiness. 

## Scopes

The 25 questions are grouped into four scopes. The grouping is for the
convenience of whoever is assessing the dataset — it does not affect scoring.

| Scope | Questions | Covers |
|---|---:|---|
| **Infrastructure** | 10 | How the dataset is hosted, accessed, licensed, and identified |
| **Metadata** | 6 | Descriptive and contextual metadata, provenance, and sampling |
| **Content** | 6 | Quality, format, and internal consistency of the data itself |
| **Ethics** | 3 | Ethical review, privacy, and legal basis |

Ethics questions apply to datasets containing human or animal subject data. For
a dataset with neither, they are answered `Yes` and marked not-applicable.

## Weighting and grades

All questions are binary, with Yes or No answers. Questions are weighted according to 
their relative importance:

| Tier | Questions | Points each | Maximum |
|---|---:|---:|---:|
| **Critical** | 9 | 80 | 720 |
| **Important** | 10 | 5 | 50 |
| **Optional** | 6 | 2 | 12 |
| | **25** | | **782** |

The sum of the points determines an overall grade for the dataset

| Grade | Threshold | Definition |
|---|---:|---|
| 🟡 **Gold** | 776 | All Critical and Important questions, plus at least half the Optional ones |
| ⚪ **Silver** | 745 | All Critical, plus at least half the Important ones (or equivalent) |
| 🟤 **Bronze** | 640 | All but one Critical question (or equivalent) |
| 🔴 **Caution** | 0 | Fails more than one Critical question — may have serious issues |


Since Critical questions are worth 80 points and everything else combined is
worth 62, no amount of Important and Optional credit can substitute for a
Critical failure.

## The metric file

The metric is given in machine readable form in [`airbds_metric.json`](airbds_metric.json). This file
carries the full question set with guidance notes, the
scopes, the weighting, and the grade thresholds – everything needed to run or
re-implement an assessment.


## The assessment skill

The [`skills/`](skills/) directory contains an **agentic skill**: a packaged set
of instructions that lets an AI assistant carry out an AIRBDS assessment for you.
Given a dataset URL, it works through all 25 questions against the published
guidance, records an answer and a justification for each, and produces a scored,
graded review.

The skill bundles its own copy of the metric and a scoring script which calculates 
points and grades based on the answers given. Assessments remain the reviewer's
responsibility: the skill produces answers, with justifying reasoning, for a human
to check.

See [`skills/README.md`](skills/README.md) for installation and usage.

## Case studies

Here you can view example assessments of four datasets against v1.0.0, chosen to
span domains and outcomes. Each link opens the completed assessment, with a comment
recorded against every question explaining the answer.

| Dataset | Resource | Score | Grade | Assessment |
|---|---|---:|---|---|
| Abbreviated Breast MRI and Digital Tomosynthesis Mammography in Screening Women With Dense Breasts | The Cancer Imaging Archive | 777 | 🟡 Gold | [Open](https://docs.google.com/spreadsheets/d/1kzExP75AunMA6gAqNec_CC-WKZO7mLNKp0-5Ff1_H3Y/edit?gid=144390565#gid=144390565) |
| Observation.org, Nature data from around the World | GBIF | 773 | ⚪ Silver | [Open](https://docs.google.com/spreadsheets/d/1rbY8nxhaX0C5x0unomQOW0d3CUfWBrbV_rdBeFow8cE/edit?gid=144390565#gid=144390565) |
| The NIST SRM 1950 plasma dataset | SRM1950 Data | 426 | 🔴 Caution | [Open](https://docs.google.com/spreadsheets/d/1xH2xL3N7riu1xUobcH-QIO24H3xBMYCy9KXx3k5ipJE/edit?gid=144390565#gid=144390565) |
| Dog10K | Dog10K | 264 | 🔴 Caution | [Open](https://docs.google.com/spreadsheets/d/1u4sZplysfEEyMnfI3hM0sfqXJtPWADi7vTquuBLPy74/edit?gid=144390565#gid=144390565) |


## Licence and citation

The metric is released under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/).

When citing, give the version from the file's `schema_version` field (currently
`1.0.1`) so it is clear which question set was used.

## Contact

Working group: [info@aibio.ac.uk](mailto:info@aibio.ac.uk) ·
[AIRBDS working group](https://aibio.ac.uk/about/working-groups/airbds/)

Issues and contributions:
[AIBIO-UK/airbds-dev](https://github.com/AIBIO-UK/airbds-dev/issues)
