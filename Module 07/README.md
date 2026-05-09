# Module 07 — Attention and Consciousness in AI
**Course:** ITAI 4374 – Neuroscience and AI
**Institution:** Houston City College
**Instructor:** Prof. Patricia McManus
**Term:** Spring 2026

---

## Overview

Module 07 explores how the brain selects and prioritizes information — and asks whether machines could ever be truly aware. It is the seventh stop in a course-long journey through the neuroscience of intelligence:

| Module | Theme |
|--------|-------|
| 02 | COMPUTE — What does the brain compute? |
| 03 | BUILD — Brain anatomy & neurons |
| 04 | CONNECT — Spiking neural networks |
| 05 | SENSE — Sensory processing & perception |
| 06 | REMEMBER — Memory & learning |
| **07** | **ATTEND & AWARE — Attention & consciousness** |

The central problem: the brain receives ~11 million bits of sensory data per second, but conscious processing handles only ~50 bits. **Attention** is the filter that bridges that gap — and transformer-based AI solves the exact same bottleneck.

---

## Folder Contents

| File | Description |
|------|-------------|
| `ITAI_4374_Module_07_Attention_and_Consciousness.pdf` | Full module booklet (38 pp.) — reading, figures, knowledge checks, glossary, references |
| `ITAI_4374_Module_07__Attention_Consciousness.pdf` | Lecture slide deck (45 slides) |
| `L07_Module07_Memory_Attention_Lab.ipynb` | Lab notebook template — all experiments, code cells, and answer stubs |
| `L07_Detailed_Instructions.docx` | Step-by-step lab instructions, grading rubric, and submission checklist |
| `L07_MairaTanweerChachar_ITAI4374.ipynb` | Completed student submission (Maira Tanweer Chachar) |

---

## Learning Objectives

By the end of this module, students are able to:

1. Explain what attention is and why the brain needs it (information bottleneck).
2. Describe Posner's three attention networks — **alerting**, **orienting**, and **executive** — and map each to its brain region.
3. Distinguish **bottom-up** (stimulus-driven) from **top-down** (goal-driven) attention with real-world examples.
4. Connect biological attention to the **transformer self-attention** mechanism used in modern AI.
5. Summarize the four major theories of consciousness: Global Workspace Theory, Integrated Information Theory, Higher-Order Theories, and Predictive Processing.
6. Articulate the **Hard Problem of consciousness** and its implications for AI safety and ethics.
7. Critically evaluate whether current AI systems possess anything resembling attention or consciousness.

---

## Module Outline

### Part 1 — How the Brain Pays Attention

| Section | Topic |
|---------|-------|
| 2 | The Brain's Spotlight — three types of attention (sustained, selective, divided) |
| 3 | Posner's Three Networks — alerting, orienting, executive; the thalamus as gatekeeper |
| 4 | Feature-Based vs. Spatial vs. Object-Based Attention; the Biased Competition Model |
| 5 | When Attention Breaks — ADHD, hemispatial neglect, Balint syndrome |

### Part 2 — AI Attention & The Consciousness Question

| Section | Topic |
|---------|-------|
| 6 | AI Attention recap through the neuroscience lens — Bahdanau (2014), self-attention, the transformer |
| 7 | Where biological and AI attention differ (emotion, Default Mode Network, energy, embodiment) |
| 8 | Four theories of consciousness — GWT, IIT, HOT, Predictive Processing |
| 9 | The Hard Problem — Chinese Room, philosophical zombies, where current AI stands |
| 10 | The Attention–Consciousness Link — subliminal priming, blindsight, AI implications |
| 11 | Big picture — practical implications for safety, ethics, and design |

---

## Lab 07 — Memory & Attention in AI Systems

The lab is a **practice audit** for the midterm project. Students test a real AI chatbot (ChatGPT, Claude, Gemini, or equivalent) and complete a **Brain vs. AI Scorecard**.

### Structure

| Part | Topic | Module | Points |
|------|-------|--------|--------|
| A | Testing AI Memory (working memory, forgetting, in-context learning) | 06 | 35 pts |
| B | Testing AI Attention (selective attention, inattentional blindness, cocktail party, attention visualization) | 07 | 30 pts |
| C | Audit Report (Brain vs. AI Scorecard + 3 reflections) | Both | 20 pts |
| D | Midterm Planning | Both | 5 pts |

### Experiments

| ID | Name | Neuroscience Concept |
|----|------|---------------------|
| A1 | Working Memory Capacity | Cowan's ~4-item limit; PFC active maintenance |
| A2 | Does the AI Forget? | Interference, Ebbinghaus forgetting curve |
| A3 | In-Context Learning | Hippocampal experience replay; CLS theory |
| B1 | Selective Attention | Top-down vs. bottom-up attention; executive network |
| B2 | Inattentional Blindness | Invisible gorilla experiment (Simons & Chabris, 1999) |
| B3 | Cocktail Party Effect | Posner alerting/orienting networks |
| B4 | Attention Visualization *(code)* | Transformer self-attention; early vs. late layer hierarchy |

### Experiment B4 — Code Setup

```python
# Install dependencies
pip install transformers torch matplotlib numpy seaborn

# Visualize self-attention on any sentence
from transformers import AutoTokenizer, AutoModel
import torch, matplotlib.pyplot as plt, seaborn as sns

model_name = "bert-base-uncased"
tokenizer  = AutoTokenizer.from_pretrained(model_name)
model      = AutoModel.from_pretrained(model_name, output_attentions=True)
model.eval()

def visualize_attention(sentence, layer=11, head=0):
    inputs = tokenizer(sentence, return_tensors="pt")
    tokens = tokenizer.convert_ids_to_tokens(inputs["input_ids"][0])
    with torch.no_grad():
        outputs = model(**inputs)
    attention = outputs.attentions[layer][0, head].numpy()
    fig, ax = plt.subplots(figsize=(10, 8))
    sns.heatmap(attention, xticklabels=tokens, yticklabels=tokens,
                cmap="Blues", ax=ax, vmin=0, vmax=0.5)
    ax.set_title(f"Attention — Layer {layer}, Head {head}")
    plt.tight_layout(); plt.show()

# Try it
visualize_attention("The cat sat on the mat because it was tired.")
```

> **Note:** The model (~400 MB) downloads on first run and is cached locally. No GPU required — CPU-only.

---

## Key Concepts (Glossary Highlights)

| Term | Definition |
|------|-----------|
| **Alerting Network** | Brain's alarm system; brainstem (locus coeruleus) + thalamus; norepinephrine-driven |
| **Orienting Network** | Brain's GPS; parietal cortex + superior colliculus; shifts attention spotlight |
| **Executive Network** | Brain's CEO; PFC + ACC; resolves conflict, directs voluntary focus |
| **Bottom-Up Attention** | Automatic, stimulus-driven (a loud bang grabs you) |
| **Top-Down Attention** | Voluntary, goal-directed (searching for your car in a lot) |
| **Inattentional Blindness** | Failing to notice a visible stimulus when attention is elsewhere (invisible gorilla) |
| **Biased Competition Model** | Neural groups compete for resources; attention tips the election (Desimone & Duncan, 1995) |
| **Global Workspace Theory** | Consciousness = information broadcast widely across the brain (Baars, 1988) |
| **Integrated Information Theory** | Consciousness = integrated information, measured by Phi (Tononi, 2004) |
| **Hard Problem** | Why does physical processing generate subjective experience? (Chalmers, 1995) |
| **Self-Attention** | Every token in a sequence checks its relevance to every other token |
| **Multi-Head Attention** | Multiple parallel attention operations, each focused on a different aspect of input |
| **Default Mode Network** | Active during rest/mind-wandering; no AI equivalent — a model is simply off |

---

## Brain ↔ AI Attention Mapping

| Brain Mechanism | AI Equivalent |
|-----------------|---------------|
| Bottom-up attention (stimulus grabs you) | High attention weights on surprising tokens |
| Top-down attention (you choose to focus) | Query vectors that specify what the model looks for |
| Orienting network (shift focus to location) | Positional encoding + attention on positions |
| Executive network (resolve conflicts) | Softmax competition — only most relevant inputs win |
| Multi-system attention (spatial + feature + object) | Multi-head attention (parallel patterns) |
| Thalamic gating (suppress irrelevant) | Low softmax weights (passive suppression) |

---

## Key Differences: Biological vs. AI Attention

| Dimension | Brain | AI |
|-----------|-------|----|
| Energy | ~20 W (whole brain) | Thousands of watts |
| Adaptability | Adapts instantly | Fixed after training |
| Emotional modulation | Amygdala hijacks attention | No emotional component |
| Context window | Effectively unlimited (via LTM) | Fixed (e.g., 128K tokens) |
| Default state | Default Mode Network active | Simply off |
| Consciousness | Linked to subjective awareness | No evidence of awareness |

---

## Midterm Connection

This lab is a **direct rehearsal** for the Midterm Pilot Audit:

- The midterm requires **3+ experiments across 3 course modules**.
- This lab provides **7 experiments across 2 modules** (06 + 07).
- Students need only add **1 more module** to meet the midterm minimum.
- All screenshots, transcripts, and scorecard rows produced here carry directly into the midterm evidence folder.

---

## References (Selected)

- Baars, B. J. (1988). *A Cognitive Theory of Consciousness.* Cambridge University Press.
- Bahdanau, D., Cho, K., & Bengio, Y. (2014). Neural machine translation by jointly learning to align and translate. *arXiv:1409.0473.*
- Chalmers, D. J. (1995). Facing up to the problem of consciousness. *Journal of Consciousness Studies, 2*(3), 200–219.
- Cherry, E. C. (1953). Some experiments on the recognition of speech. *JASA, 25*(5), 975–979.
- Desimone, R., & Duncan, J. (1995). Neural mechanisms of selective visual attention. *Annual Review of Neuroscience, 18*, 193–222.
- Posner, M. I. (1980). Orienting of attention. *QJEP, 32*(1), 3–25.
- Searle, J. R. (1980). Minds, brains, and programs. *BBS, 3*(3), 417–424.
- Simons, D. J., & Chabris, C. F. (1999). Gorillas in our midst. *Perception, 28*(9), 1059–1074.
- Tononi, G. (2004). An information integration theory of consciousness. *BMC Neuroscience, 5*(1), 42.
- Vaswani, A., et al. (2017). Attention is all you need. *NeurIPS, 30.*

---

*ITAI 4374 · Houston City College · Professor Patricia McManus · Spring 2026*
