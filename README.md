# FitAug-1.2M

FitAug-1.2M is a large-scale image-text augmentation dataset for vision-language-model (VLM) based fitness guidance.

## Overview

FitAug-1.2M is introduced to support more reliable and fine-grained VLM-based fitness coaching. Our goal is not only to build a larger fitness dataset, but to enrich the supervision modality with high-quality, professionally grounded textual guidance for movement assessment and coaching.

In particular, we target a practical gap in current VLM fitness guidance systems: many models can generate fluent feedback, but they still lack sufficiently reliable, expert-level supervision for correctness-sensitive movement understanding and actionable coaching.

![Dataset Overview](assets/images/dataset.png)

## Why FitAug-1.2M

We build FitAug-1.2M to provide large-scale, high-quality image-text supervision for fitness guidance, with a particular focus on professional movement instruction.

Rather than collecting generic action descriptions, we construct expert-oriented guidance annotations that describe whether a movement is correct, why it is incorrect, and how it should be corrected. This makes the dataset suitable for training and analyzing VLMs for practical fitness coaching rather than generic action recognition alone.

## Data Sources

FitAug-1.2M is built from publicly available visual resources for fitness and action understanding. The source pool includes fitness-related datasets and publicly accessible online video materials covering home, commercial gym, and outdoor workout scenarios.

To improve diversity and practical relevance, we intentionally collect visual material with variation in viewpoint, environment, user appearance, and exercise execution. While the visual content is drawn from public resources, all task-oriented guidance annotations in FitAug-1.2M are newly created under our unified annotation protocol.

## Annotation Pipeline

FitAug-1.2M is annotated through a multi-stage expert-guided pipeline designed to ensure both professional quality and large-scale coverage.

First, certified coaches annotate the visual data based on domain-specific instructional knowledge and professional exercise standards described in our paper. The annotations focus on exercise correctness, error identification, rationale analysis, and corrective feedback.

Second, the annotated samples are reviewed by another expert to ensure consistency, correctness, and instructional value. Only samples that pass expert review are retained as seed supervision.

Third, based on the validated expert annotations, we use large language models to expand the textual supervision in a controlled way. This expansion is guided by expert-designed templates and structured metadata so that the generated text remains semantically diverse while preserving professional correctness.

This pipeline allows us to combine expert reliability with scalable text augmentation.

![PCI Annotation Pipeline](assets/images/pci.png)

## Dataset Scale

The final dataset contains large-scale image-text supervision for apparatus-centric fitness guidance, including expert-validated annotations and expanded textual guidance.

FitAug-1.2M includes:

- 9,611 curated image sequences
- 263 expert-authored question templates
- 531 expert-authored answer templates
- 1,208,340 human-vetted image-text QA pairs

The dataset focuses on four representative apparatus-centric exercises:

- Barbell Row
- Bench Press
- Back Squat
- Overhead Press

It covers 14 scenario types and 34 fine-grained error types.

## Benchmark and Evaluation

Beyond dataset construction, our broader study also examines how well current VLMs perform on fitness guidance.

We evaluate VLMs under a fine-grained benchmark setting rather than relying on coarse or single-dimensional scoring. This benchmark is designed to measure whether a model can provide useful, reliable, and instructionally meaningful fitness guidance across multiple coaching abilities.

![Benchmark Overview](assets/images/main.png)

## 5D Evaluation Dimensions

To evaluate VLM-based fitness guidance more comprehensively, we introduce a 5-dimensional subjective evaluation framework covering:

- **Motivational Encouragement (ME)**  
  Whether the model provides supportive and motivating coaching language

- **Program Design (PD)**  
  Whether the model gives reasonable and structured training advice

- **Macronutrient Allocation (MA)**  
  Whether the model provides appropriate nutrition-related guidance

- **Equipment Recognition (ER)**  
  Whether the model correctly understands the exercise equipment and context

- **Movement Assessment (MAs)**  
  Whether the model correctly judges movement quality and provides useful corrective guidance

This 5D framework is designed to capture coaching competence more comprehensively than movement-only evaluation.

## PCI for Movement Assessment

Movement assessment remains the most correctness-sensitive part of fitness guidance. To better diagnose model performance in this dimension, we further introduce **Progressive Competence Isolation (PCI)**.

PCI decomposes movement assessment into four sequential stages:

- **Exercise Identification (EI)**
- **Technique Judgment (TJ)**
- **Movement Analysis (MAn)**
- **Prescriptive Suggestion (PS)**

This stage-wise protocol allows us to analyze where a model succeeds or fails within the movement-assessment pipeline, rather than treating the whole task as a single black-box score.

In our benchmark analysis, we find that many models can produce plausible explanations or suggestions, yet remain much weaker at correctness-sensitive technique judgment. In practice, this means a model may sound helpful before it can reliably judge whether a movement is actually correct.

FitAug-1.2M is built to address exactly this gap.

## Benchmark Leaderboard

Using the 5D framework and PCI-based movement analysis, we build the FitGuid benchmark and evaluate a broad range of open-source and closed-source VLMs.

The leaderboard is included in this repository to provide a practical reference for model selection. It helps users compare models not only by overall performance, but also by their strengths and weaknesses across different coaching dimensions and movement-assessment stages.

In short:

- **FitGuid** shows where current models fail.
- **PCI** shows at which stage they fail.
- **FitAug-1.2M** provides targeted data to improve those failures.

## What this repository provides

This repository contains:

- an overview of the dataset and its design goals,
- documentation of the annotation and evaluation pipeline,
- a public subset of the data,
- benchmark-related materials and leaderboard results,
- access information for the full dataset release.

## Scope

FitAug-1.2M is designed for targeted model improvement in VLM-based fitness guidance, especially for movement assessment and expert-style corrective feedback. It is not intended as a generic action recognition dataset.

## Access

A public subset is provided in this repository.  
For access to the full dataset, please contact the authors via email and briefly describe your affiliation, intended use, and research purpose.

## Citation

If you find this dataset useful, please cite our paper.