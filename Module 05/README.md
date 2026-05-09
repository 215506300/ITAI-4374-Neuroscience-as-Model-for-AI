# Module 05 — Sensory Processing & AI Perception
**Course:** ITAI 4374 — Bachelor of Applied Technology in AI & Robotics  
**Institution:** Houston City College  
**Term:** Spring 2026

---

## Overview

This module explores how biological sensory systems convert physical energy into neural representations — and how those biological principles directly inspired modern AI architectures. Students trace the path from retinal ganglion cells to convolutional neural networks, from cochlear tonotopy to mel-frequency spectrograms, and examine where AI perception still falls short of its biological counterpart.

---

## Learning Objectives

By the end of this module, students will be able to:

1. Describe how biological sensory systems convert physical energy into neural representations
2. Explain the visual cortex hierarchy (V1 → IT) and its relationship to CNN architecture
3. Compare all five sensory systems, identifying shared organizational principles
4. Analyze how biological sensing inspired CNNs, spectrograms, and event-based vision
5. Evaluate strengths and limitations of biological vs. artificial perception

---

## Folder Contents

| File | Type | Description |
|------|------|-------------|
| `ITAI_4374_Module_05_Sensor_and_Perception.pdf` | Lecture Slides | Full slide deck for Module 05 — covers sensation vs. perception, the six principles of sensory systems, visual hierarchy, auditory pathway, somatosensory/gustatory/olfactory systems, CNN mapping, event-based vision, multisensory integration, and the binding problem |
| `ITAI_4374_Module_05_Booklet_Sensory_Processing.docx` | Reading Booklet | Companion reading booklet for Module 05 sensory processing content |
| `L05_Module05_Sensory_Processing_Lab__1_.ipynb` | Lab Notebook | Lab 05 template — Bio-Inspired Perception Pipeline. Students build center-surround DoG filters (retinal processing), a Gabor filter bank (V1/simple cells), extract CNN first-layer filters for comparison, and trace hierarchical activation maps across layers |
| `L05_Maira_Tanweer_Chachar_ITAI4374__1_.ipynb` | Student Submission | Completed Lab 05 submission by Maira Tanweer Chachar |

---

## Module Structure

The lecture is organized into three parts:

**Part 1 — How the Brain Perceives the World**  
Sensation vs. perception, the six principles of all sensory systems (transduction, hierarchical processing, parallel pathways, topographic mapping, lateral inhibition, top-down modulation), retinal anatomy and center-surround receptive fields, the LGN M/P pathways, Hubel & Wiesel's V1 discoveries, the visual cortex hierarchy (V1 → V2 → V4 → IT), and the ventral/dorsal "what vs. where" streams. Covers the auditory system (cochlea, tonotopy, auditory pathway), somatosensory system (homunculus, proprioception), and gustatory/olfactory systems.

**Part 2 — From Biology to AI Systems**  
Timeline from Hubel & Wiesel (1962) → Neocognitron (1980) → LeNet (1989) → AlexNet (2012). Feature-by-feature mapping of biology to CNN components (simple cells = conv filters, complex cells = pooling layers). CNN feature visualization (Zeiler & Fergus 2014) confirming layers match V1 → V2 → V4 → IT. Event-based vision (DVS cameras as silicon retinas) and bio-inspired pipeline to neuromorphic hardware.

**Part 3 — Multimodal Integration & Frontiers**  
Three rules of multisensory integration (spatial, temporal, inverse effectiveness), the McGurk Effect, multimodal AI (CLIP, GPT-4V, sensor fusion), the binding problem, and a head-to-head comparison of where biology wins vs. where AI excels.

---

## Lab — Bio-Inspired Perception Pipeline

Students implement a complete perceptual hierarchy in Python:

- **Part A:** Center-surround Difference-of-Gaussians (DoG) filters — mimicking retinal ganglion cells
- **Part B:** Gabor filter bank at multiple orientations — mimicking V1 simple cells
- **Part C:** Extract first-layer filters from VGG/ResNet and compare to the Gabor bank
- **Part D:** Trace activation maps across early, mid, and late CNN layers, mapping to V1 → V2 → V4 → IT
- **Part E:** Reflection — where do bio-inspired filters match learned CNN filters, and where do they diverge?

---

## Key Concepts

- Sensation vs. perception; perception as active construction
- Six principles shared by all sensory systems
- Center-surround receptive fields → edge detection → CNN conv filters
- Retinotopy / tonotopy / somatotopy as the same topographic mapping principle
- Magnocellular vs. parvocellular pathways → SlowFast networks
- Ventral stream (what) vs. dorsal stream (where/how) — and why robotics needs both
- Biological Fourier transform in the cochlea → mel-frequency spectrograms
- DVS event cameras as literal silicon retinas
- The binding problem — unsolved in both neuroscience and AI

---

## Connections to Other Modules

| Module | Connection |
|--------|-----------|
| Module 02 | Predictive coding and top-down modulation (Principle 6) |
| Module 03 | LIF neurons and neural coding in sensory pathways |
| Module 04 | STDP, SNNs, and neuromorphic hardware as the downstream target of DVS cameras |
| Module 06 | Memory and learning architectures — from perceiving the world to remembering it |

---

## Supplemental Readings

See the `Supplemental_Readings/` folder for four peer-reviewed and scholarly readings that extend module topics into predictive processing, clinical sensory integration, recurrent processing theory, and fitness-maximizing sensory codes.

---

*ITAI 4374 — Houston City College — Spring 2026*
