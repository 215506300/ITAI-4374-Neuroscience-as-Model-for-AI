# ITAI 4374 — Module 05: Sensory Processing & AI Perception

**Course:** Bachelor of Applied Technology in AI & Robotics  
**Institution:** Houston City College  
**Term:** Spring 2026

---

## Overview

This module explores how biological sensory systems work and how they have inspired modern AI perception systems. It covers the full arc from biological sensation to neural representation to AI architecture — with the visual cortex → CNN connection as the central case study.

---

## Files in This Folder

| File | Description |
|------|-------------|
| `ITAI_4374_Module_05_Sensor_and_Perception.pdf` | Lecture slide deck — covers all three parts of the module |
| `ITAI_4374_Module_05_Booklet_Sensory_Processing.docx` | Reading booklet with expanded explanations and notes |
| `L05_Module05_Sensory_Processing_Lab__1_.ipynb` | Lab notebook — bio-inspired perception pipeline (starter) |
| `L05_Maira_Tanweer_Chachar_ITAI4374__1_.ipynb` | Completed student lab submission |

---

## Learning Objectives

By the end of this module, you will be able to:

1. Describe how biological sensory systems convert physical energy into neural representations
2. Explain the visual cortex hierarchy (V1 → IT) and its relationship to CNN architecture
3. Compare all five sensory systems and identify shared organizational principles
4. Analyze how biological sensing inspired CNNs, spectrograms, and event-based vision
5. Evaluate the strengths and limitations of biological vs. artificial perception

---

## Module Structure

### Part 1 — How the Brain Perceives the World
- Sensation vs. perception
- Six principles shared by all sensory systems (transduction, hierarchy, parallel pathways, topographic mapping, lateral inhibition, top-down modulation)
- The retina, center-surround receptive fields, and the LGN
- Hubel & Wiesel: simple cells, complex cells, hypercomplex cells
- Visual hierarchy: V1 → V2 → V4 → IT
- Ventral ("what") and dorsal ("where/how") streams
- Auditory, somatosensory, gustatory, and olfactory systems

### Part 2 — From Biology to AI Systems
- Timeline: cat V1 experiments (1962) → Neocognitron → LeNet → AlexNet (2012)
- Biology-to-CNN feature mapping
- CNN feature visualization and its match to the visual hierarchy
- Event-based vision: DVS cameras as silicon retinas
- Industry applications of bio-inspired perception

### Part 3 — Multimodal Integration & Frontiers
- Three rules of multisensory integration (spatial, temporal, inverse effectiveness)
- The McGurk Effect
- Multimodal AI: CLIP, GPT-4V, sensor fusion
- The binding problem — unsolved in both neuroscience and AI
- Where biology still leads vs. where AI excels

---

## Lab: Bio-Inspired Perception Pipeline

The lab walks through five stages:

- **A** — Retinal Processing: center-surround DoG filters mimicking ganglion cells  
- **B** — V1 Processing: Gabor filter bank at multiple orientations (= simple cells)  
- **C** — CNN Comparison: first-layer filters from VGG/ResNet vs. Gabor bank  
- **D** — Hierarchical Activation Maps: early → mid → late layers mapped to V1 → V2 → V4 → IT  
- **E** — Reflection: where bio filters match CNN filters, and where they diverge

---

## Key Concepts

- **Transduction** — converting physical energy into electrical neural signals
- **Retinotopy / Tonotopy / Somatotopy** — topographic maps preserved across sensory modalities
- **Center-Surround Receptive Fields** — the retina's edge-detection computation; analogous to Laplacian of Gaussian (LoG) filters
- **Ventral vs. Dorsal Stream** — "what" vs. "where/how" pathways; most CV systems implement ventral only
- **DVS Camera** — dynamic vision sensor; a silicon retina that fires on brightness changes rather than capturing frames
- **Binding Problem** — how the brain unifies distributed features into a single coherent percept; currently unsolved

---

## Connection to Other Modules

| Module | Topic |
|--------|-------|
| Module 02 | Thousand Brains Theory, Predictive Coding |
| Module 03 | Brain Anatomy, LIF Neurons, Neural Coding |
| Module 04 | Spiking Neural Networks, STDP, Neuromorphic Hardware |
| **Module 05** | **Sensory Processing & AI Perception** ← you are here |
| Module 06 | Memory, Learning, and AI Architectures |
