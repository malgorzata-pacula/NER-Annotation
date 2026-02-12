# Named Entity Recognition (NER) Annotation – Case Study

## Overview

This repository presents a manual **Named Entity Recognition (NER)** annotation case study completed using **Label Studio**.  
The project demonstrates high-quality, span-based entity annotation with strict schema adherence, careful boundary selection, and documented decision-making for ambiguous cases.

All annotations were performed manually with the goal of producing clean, machine-readable data suitable for training and evaluating NLP models.

---

## Objective

The objectives of this project were to:

- Demonstrate practical experience with NER annotation workflows  
- Apply a fixed entity schema consistently across a dataset  
- Handle ambiguity using principled annotation decisions and comments  
- Produce structured outputs aligned with real-world ML pipelines  

---

## Dataset

- **60 short text samples**
- Mixed content, including:
  - News-style sentences
  - Institutional and organizational references
  - Everyday language
- The dataset intentionally includes:
  - Clear entity mentions
  - Ambiguous cases
  - Titles vs. proper names
  - Absolute and relative temporal expressions  

Input data is provided in both CSV and JSON formats.

---

## Entity Schema

A fixed schema was defined and strictly followed throughout the project.

| Entity Type   | Description |
|--------------|-------------|
| Person       | Named individuals (proper names only) |
| Organization | Companies, institutions, government bodies, media outlets |
| Location     | Geographical locations (cities, countries, regions, landmarks) |
| Date         | Absolute and relative temporal expressions |

No additional entity types were introduced during annotation.

---

## Tooling & Configuration

- **Annotation platform:** Label Studio  
- **Annotation type:** Manual, span-based  
- **Input format:** CSV  
- **Output format:** JSON  

The labeling interface was configured to allow:
- Precise text span selection
- Multiple entity labels per text
- Optional annotation comments for decision documentation

### Labeling Template Example

Below is the Label Studio configuration used to define the NER task and entity schema:

![NER labeling template](https://raw.githubusercontent.com/malgorzata-pacula/NER-Annotation/main/images/NER-labelling.png)

---

## Annotation Methodology

The annotation process followed these core principles:

### Span Precision
- Only exact entity names were annotated
- No leading or trailing whitespace included
- Titles and descriptive modifiers excluded unless explicitly part of the entity

### Schema Discipline
- Entities were labeled strictly according to the predefined schema
- Mentions not clearly belonging to an allowed entity type were excluded

### Context-Aware Decisions
- Annotation decisions were based on sentence context, not recognizability alone
- The same surface form could be included or excluded depending on usage

### Conservative Labeling
- In ambiguous cases, under-labeling was preferred over speculative labeling

---

## Handling Ambiguity

Special attention was given to borderline cases, including:

- Job titles without explicit person names
- Organization names used as descriptors
- Nested entities (e.g. locations within organization names)
- Generic nouns resembling entities
- Relative date expressions (e.g. “yesterday”, “last Friday”)

In such cases, concise annotation comments were added to explain the rationale.

### Annotated Entry Example

The screenshot below shows a completed annotation with an explanatory comment documenting schema decisions:

![NER annotated entry](https://raw.githubusercontent.com/malgorzata-pacula/NER-Annotation/main/images/NER-entry.png)

---

## Quality Control

Quality assurance focused on:

- Correct entity type assignment
- Clean and consistent span boundaries
- Uniform schema application across all samples
- Minimal but meaningful annotation comments

The final dataset reflects consistency suitable for downstream NLP tasks.

---

## Outputs

The exported annotation data includes:

- Span-based entity labels
- Character offsets for each entity
- Entity type assignments
- Optional annotation comments
- Annotation metadata (e.g. lead time)

The outputs are suitable for:
- Model training
- Evaluation datasets
- Further processing in ML pipelines

---

## Skills Demonstrated

- Named Entity Recognition (NER)
- Span-based annotation
- Annotation guideline interpretation
- Ambiguity handling and documentation
- Label Studio configuration and usage
- Quality-focused human-in-the-loop workflows

---

## Files in This Repository
```text
.
NER-Annotation/
├── data/
│ ├── NER-portfolio.csv
│ └── NER-portfolio.json
├── images/
│ ├── NER-labelling.png
│ └── NER-entry.png
├── docs/
│ ├── Guidelines_NER_Annotation.pdf
│ └── Case_Study_NER_Annotation.pdf
└── README.md
```
