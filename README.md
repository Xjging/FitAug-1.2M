# FitAug-1.2M

FitAug-1.2M is a large-scale image-text augmentation dataset for vision-language-model (VLM) based fitness guidance. It is designed to provide PCI-aligned supervision for movement assessment and targeted model refinement, with a particular focus on apparatus-centric resistance training scenarios. The dataset is introduced in our paper *“5D Subjective Evaluation of VLM Fitness Guidance: Alignment, Diagnosis, Benchmark, and 1.2M Image-Text Dataset”*. :contentReference[oaicite:1]{index=1}

## Overview

Recent VLMs have shown strong potential for scalable fitness guidance, yet our benchmark analysis reveals a persistent weakness in **technique judgment (TJ)** within movement assessment. To address this bottleneck, we construct **FitAug-1.2M**, a PCI-aligned augmentation corpus that supports four sequential movement-assessment stages:

- **EI**: Exercise Identification  
- **TJ**: Technique Judgment  
- **MAn**: Movement Analysis  
- **PS**: Prescriptive Suggestion  

FitAug-1.2M is built to complement the **FitGuid** benchmark and provide targeted supervision for improving stage-wise fitness guidance performance. :contentReference[oaicite:2]{index=2}

## Dataset Scope

FitAug-1.2M focuses on four representative apparatus-centric exercises:

- **Barbell row**
- **Bench press**
- **Back squat**
- **Overhead press**

Across these exercises, the dataset covers **14 scenario types** and **34 fine-grained error types**, enabling structured supervision for exercise recognition, correctness judgment, error diagnosis, and corrective coaching suggestions. :contentReference[oaicite:3]{index=3}

## Data Composition

The dataset contains:

- **9,611 curated image sequences**
- **263 expert-authored question templates**
- **531 expert-authored answer templates**
- **1,208,340 human-vetted image-text QA pairs**

Each sample is aligned with the PCI protocol and supports one or more of the four movement-assessment stages. Compared with prior datasets for vision-based fitness guidance, FitAug-1.2M is distinguished by its PCI-ready staged annotations, apparatus awareness, and large-scale image-text supervision. :contentReference[oaicite:4]{index=4}

## Data Sources and Curation

FitAug-1.2M is constructed from publicly available visual sources, including fitness- and action-related datasets and online video resources. Only the **visual material** is reused; all annotations are **newly created** under a unified PCI-aligned protocol. The source pool spans home, commercial gym, and outdoor environments, with diverse viewpoints, scene complexity, genders, body types, and racial backgrounds. :contentReference[oaicite:5]{index=5}

The curation pipeline includes:

1. collecting candidate clips from public sources,
2. filtering low-quality or ambiguous visual content,
3. sampling frames at approximately **1.5–2 fps**,
4. pruning non-exercise or off-moment frames by experts,
5. assigning PCI stage-aligned labels under a unified annotation protocol. :contentReference[oaicite:6]{index=6}

## Annotation Pipeline

Certified coaches define the exercise taxonomy, scenario types, and fine-grained error categories, and provide PCI-consistent seed annotations for EI, TJ, MAn, and PS. Based on these seeds, coaches further author question and answer templates that capture key coaching cues. Candidate QA pairs are then synthesized with GPT-5 using the templates and scenario metadata, and finally reviewed, corrected, or discarded by coaches before inclusion. This process yields a large-scale yet human-vetted supervision corpus for VLM fitness guidance. :contentReference[oaicite:7]{index=7}

## Benchmark Separation

To avoid train-test leakage, FitAug-1.2M is constructed from data sources that are **strictly disjoint** from those used in the FitGuid benchmark, with enforced sample-level separation from benchmark evaluation items. This makes the dataset suitable for augmentation, fine-tuning, and controlled benchmarking studies. :contentReference[oaicite:8]{index=8}

## Intended Use

FitAug-1.2M is intended for:

- supervised fine-tuning of open-source VLMs,
- stage-wise training for PCI-based movement assessment,
- error-type-aware fitness guidance modeling,
- research on trustworthy and diagnostically precise AI fitness coaching.

In our paper, fine-tuning on FitAug-1.2M consistently improves performance across all PCI stages and substantially boosts end-to-end movement assessment results on FitGuid. :contentReference[oaicite:9]{index=9}# FitAug-1.2M
