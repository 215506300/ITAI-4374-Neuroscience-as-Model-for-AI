# Module 06: Memory, Learning, and AI Architectures
### ITAI 4374 — Neuroscience as a Model for AI
**Houston City College | AI & Robotics Program | Professor Patricia McManus**
*From Remembering to Reasoning*

---

## 📁 Folder Contents

| File | Type | Description |
|------|------|-------------|
| `ITAI_4374_Module_06__Memory_and_learning.pdf` | Slide Deck | Full lecture presentation for Module 06 |
| `ITAI_4374_Module_06_Booklet_Memory__Learning.pdf` | Student Booklet | Comprehensive reading booklet with figures, AI connections, knowledge checks, glossary, and references |
| `WhereIstheAnterior_Temporal_LobeandWhatDoesItDo.pdf` | Supplemental Reading | Peer-reviewed journal article (Bonner & Price, 2013) — *Journal of Neuroscience* |

---

## 🧠 Module Overview

Module 06 bridges neuroscience and AI by examining how biological memory systems work — and how those systems have inspired (or should inspire) AI architectures. The module is divided into two parts:

**Part 1 — How the Brain Remembers** (Conceptual, no math required)
**Part 2 — How AI Remembers, and What It Gets Wrong** (Computational parallels, with optional math)

---

## 📚 Learning Objectives

By the end of this module, students will be able to:

1. Explain the four biological memory systems (working, episodic, semantic, procedural) and identify which brain structures support each
2. Describe how the hippocampus consolidates memories during sleep — and why this matters for AI
3. Connect hippocampal replay to experience replay in Deep Reinforcement Learning
4. Compare AI memory architectures (LSTMs, Transformers, MANNs, RAG) to their biological inspirations
5. Articulate the biological plausibility debate around backpropagation and evaluate alternative learning algorithms
6. Evaluate which biological memory principles AI has successfully adopted and which remain open challenges

---

## 🗂️ Module Structure

### Part 1 — How the Brain Remembers

| Section | Topic |
|---------|-------|
| Section 1 | Welcome — Why Memory Changes Everything (H.M. / Henry Molaison case) |
| Section 2 | The Four Memory Systems — Working, Episodic, Semantic, Procedural |
| Section 3 | The Hippocampus — The Brain's Memory Engine (trisynaptic circuit, consolidation, experience replay, place cells & grid cells) |
| Section 4 | Complementary Learning Systems (CLS) — Solving Catastrophic Forgetting |
| Section 5 | How the Brain Learns — LTP, LTD, Neuromodulators, Sleep Stages |

### Part 2 — How AI Remembers

| Section | Topic |
|---------|-------|
| Section 6 | AI Memory Architectures — LSTMs, Transformers, MANNs, RAG |
| Section 7 | The Biological Plausibility Debate — Backprop vs. Hebbian, Feedback Alignment, Predictive Coding, Forward-Forward |
| Section 8 | The Big Picture — Biology → AI Status Table |
| Section 9 | Lab Preview — Human vs. AI Memory Performance |
| Section 10 | Module Summary — 6 Key Takeaways |
| Section 11 | Bridge to Module 07 — Attention & Consciousness in AI |
| Section 12 | Glossary |
| Section 13 | References & Further Reading |

---

## 🔑 Key Concepts

- **Four Memory Systems:** Working (PFC / context window), Episodic (Hippocampus / RAG), Semantic (Cortex / model weights), Procedural (Basal ganglia / RL policies)
- **Henry Molaison (H.M.):** The foundational patient case proving memory is not one system
- **Hippocampal Trisynaptic Circuit:** Entorhinal Cortex → Dentate Gyrus (pattern separation) → CA3 (pattern completion) → CA1 (novelty detection)
- **Memory Consolidation:** Two-system architecture — fast hippocampal encoding + slow cortical consolidation during sleep
- **Experience Replay:** Hippocampal sleep replay → DeepMind's DQN (2013); prioritized replay mirrors emotional tagging
- **Place Cells & Grid Cells:** Nobel Prize 2014; AI navigation networks spontaneously develop grid cell-like patterns (Banino et al., 2018)
- **Complementary Learning Systems (CLS):** McClelland, McNaughton & O'Reilly (1995) — the solution to catastrophic forgetting
- **LTP / LTD:** The brain's bidirectional weight update mechanism; NMDA receptor as coincidence detector
- **Neuromodulators:** Dopamine (surprise/reward → TD error), Acetylcholine (attention → learning gate), Norepinephrine (arousal → explore vs. exploit)
- **Biological Plausibility Debate:** Backprop vs. Hebbian learning, Feedback Alignment, Predictive Coding, Forward-Forward Algorithm
- **RAG (Retrieval-Augmented Generation):** Most practical AI memory today; mirrors hippocampal-cortical distinction

---

## 🔗 Connections to Other Modules

| Module | Connection |
|--------|------------|
| Module 02 | Free Energy Principle / Predictive Coding — revisited in Section 7 (bio-plausible learning) |
| Module 03 | Brain anatomy (hippocampus, PFC, basal ganglia, amygdala) introduced; deepened here |
| Module 04 | Hebbian learning, STDP, spiking neurons — cellular basis of LTP/LTD |
| Module 05 | Sensory processing (ventral visual stream hierarchy) connects to ATL semantic memory (supplemental reading) |
| Module 07 | Attention & Consciousness — next step after memory in the SENSE → REMEMBER → ATTEND arc |

---

## 📖 Supplemental Reading — Summary

**Bonner, M.F. & Price, A.R. (2013)**
*"Where Is the Anterior Temporal Lobe and What Does It Do?"*
Journal of Neuroscience, 33(10), 4213–4215.

This Journal Club article reviews a key fMRI study (Peelen & Caramazza, 2012) on the **anterior temporal lobe (ATL)** and its role in **semantic memory**. Key points:

- The ATL is implicated in semantic memory via semantic dementia patient studies
- fMRI evidence is inconsistent due to imaging artifacts and ATL anatomical heterogeneity
- Peelen & Caramazza found that the **ventral temporal pole** encodes abstract conceptual properties of objects (location, action features)
- Supports a **hierarchical processing model** along the ventral visual stream (perceptual → conceptual)
- Challenges the purely **amodal hub** theory of ATL — suggests modality-specific subregions (ventral = visual concepts; lateral = auditory/linguistic concepts)
- Connects directly to Module 06's discussion of **semantic memory** as distributed cortical representation

---

## 🧪 Lab Assignment

**Lab 06 — Pattern Recognition: Human vs. AI Memory**
- Part A: Human memory tasks (free recall, recognition, serial recall)
- Part B: LSTM & Transformer memory tasks in Python/Wolfram (sequence length, primacy/recency effects)
- Part C: Written reflection comparing biological vs. artificial memory
- Tools: Google Colab or Wolfram Cloud

---

## 📌 Discussion Prompt

> *"If you could give an AI system ONE biological memory feature it currently lacks, which would you choose and why?"*

---

## ➡️ Next Module

**Module 07 — Attention & Consciousness in AI**
Biological attention circuits → Global Workspace Theory → Transformer attention mechanisms → The hard problem of consciousness
