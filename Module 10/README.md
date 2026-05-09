# Module 10 — Neuro-Symbolic AI & Architectures
**Course:** ITAI 4374 – Neuroscience and AI
**Institution:** Houston City College
**Instructor:** Prof. Patricia McManus
**Term:** Spring 2026


---

> *"Can a machine that recognizes faces also understand WHY? Bridging perception and logic."*

---

## Overview

This module introduces **Neuro-Symbolic AI** — the integration of neural network perception with symbolic logical reasoning. The central argument: neither approach alone is sufficient for human-like intelligence, but together they mirror how the biological brain actually works.

The lab (Part 4) implements a working neuro-symbolic pipeline: a **Python/TensorFlow neural classifier** converts visual clue icons into symbolic labels, which are then passed to a **Wolfram Language constraint solver** that reasons over the labels to solve a logic puzzle.

---

## The Puzzle

A simplified three-house logic puzzle (Zebra/Einstein style):

| Variable   | Possible Values          |
|------------|--------------------------|
| Colors     | Red, Blue, Green         |
| Pets       | Cat, Dog, Fish           |
| Beverages  | Coffee, Tea, Juice       |

**Clues (presented as visual icons, classified by the neural layer):**

1. The person in the **Red** house drinks **Coffee**.
2. The person who owns the **Dog** lives in **House 2** (middle).
3. The **Green** house is immediately to the right of the **Blue** house.
4. The **Tea** drinker owns the **Cat**.
5. The **Juice** drinker lives in the **Green** house.

---

## Architecture

```
[ Visual Clue Icons ]
        │
        ▼
[ Python · TensorFlow CNN ]   ← Neural Layer (perception)
        │  classifies icons → symbolic labels
        ▼
[ clue_labels.json ]          ← Bridge (structured data handoff)
        │
        ▼
[ Wolfram Language · Solve[] ] ← Symbolic Layer (reasoning)
        │  applies constraints → finds unique solution
        ▼
[ Solution + Reasoning Trace ]
```

This is the **Sequential integration strategy**: neural perception feeds symbolic reasoning.
It mirrors the brain's own pipeline: **visual cortex (System 1) → prefrontal cortex (System 2)**.

---

## Setup & Requirements

### Python Environment

```bash
pip install tensorflow keras numpy pillow wolframclient
```

> Tested with Python 3.10+, TensorFlow 2.15+

### Wolfram Language

- **Option A:** [Wolfram Engine (free for developers)](https://www.wolfram.com/engine/) + `wolframclient` Python library
- **Option B:** Wolfram Desktop or Mathematica (campus license)
- **Option C:** File-based pipeline — Python writes JSON, Wolfram script reads it (simplest; recommended for first run)

---

## Running the Lab

### Step 1 — Train the Neural Classifier (Part B)

```bash
cd neural/
python train_classifier.py
```

Trains a small CNN on the icon dataset. Saves weights to `model/icon_classifier.keras`.
Expected training time: < 2 minutes on CPU.

### Step 2 — Classify the Puzzle Clues (Part D, neural half)

```bash
python predict_clues.py
```

Runs the trained model on the 5 puzzle clue images.
Outputs `bridge/clue_labels.json` with predicted labels and confidence scores.

**Example output:**
```json
{
  "clue_1_color": "red",
  "clue_1_drink": "coffee",
  "clue_2_pet": "dog",
  "clue_2_position": 2,
  "clue_3_relation": "green_right_of_blue",
  "clue_4_drink": "tea",
  "clue_4_pet": "cat",
  "clue_5_color": "green",
  "clue_5_drink": "juice"
}
```

### Step 3 — Solve with Wolfram Language (Part C)

Open `symbolic/puzzle_solver.wl` in Wolfram Desktop / Mathematica, or run via terminal:

```bash
wolframscript -file symbolic/puzzle_solver.wl
```

### Step 4 — Run the Full Pipeline (Part D, integrated)

```bash
cd bridge/
python run_pipeline.py
```

Calls Steps 2 and 3 in sequence. Writes the solution and reasoning trace to `outputs/`.

---

## Expected Solution

```
House 1: Blue  | Tea    | Cat
House 2: Red   | Coffee | Dog
House 3: Green | Juice  | Fish
```

---

## Key Concepts Demonstrated

| Concept | Where in the Code |
|---|---|
| Neural pattern recognition | `train_classifier.py` (CNN) |
| Symbolic constraint solving | `puzzle_solver.wl` (Wolfram `Solve[]`) |
| Sequential integration strategy | `run_pipeline.py` (JSON bridge) |
| System 1 → System 2 handoff | `predict_clues.py` output → `puzzle_solver.wl` input |
| Explainability | `reasoning_trace.txt` (every step logged) |
| Brittleness test | Part E — inject a misclassification and observe solver behavior |

---

## Lab Reflection Questions (Part E)

Answer these in your lab report:

1. Which icons did the classifier handle with highest/lowest confidence? Why?
2. Trace through the Wolfram solver step-by-step. Which clue eliminated the most possibilities first?
3. Could the neural classifier solve the puzzle alone? Could the Wolfram solver work without the classifier?
4. What happens when you deliberately misclassify one icon (e.g., red → green)? Does the solver detect the inconsistency or produce a wrong answer silently?
5. How does this pipeline compare to how *you* solved the puzzle by hand?

---

## Extension Challenge

Add a sixth clue — e.g., `"The Fish owner lives in House 1"` — and:

- Add the corresponding visual icon to the clue set
- Update `predict_clues.py` to classify it
- Add the new constraint to `puzzle_solver.wl`
- Re-run the full pipeline

Then try adding a **contradictory** clue (one that makes the puzzle unsolvable). Observe how the Wolfram solver responds vs. how a neural network would respond. Document your findings.

---

## Real-World Parallels

| This Lab | Real System | Integration Type |
|---|---|---|
| CNN icon classifier → Wolfram solver | Google Search (neural ranking + Knowledge Graph) | Sequential |
| Physics rules as constraints | AlphaFold (neural + biophysics rules) | Guided |
| Traceable reasoning chain | MYCIN medical diagnosis (600 IF-THEN rules) | Symbolic |
| Shared JSON bridge | LangChain agent framework | Global Workspace |

---

## Module Learning Objectives

By completing this module and lab, you will be able to:

- [x] Explain why neural networks excel at perception but struggle with logical reasoning
- [x] Describe the four integration strategies: Sequential, Guided, Compiled, Bidirectional
- [x] Connect Kahneman's System 1/2 framework to neuro-symbolic architectures
- [x] Explain Global Workspace Theory as an AI architecture blueprint
- [x] Identify real-world neuro-symbolic systems (AlphaFold, Google Search, DreamCoder)
- [x] Build a working sequential neuro-symbolic pipeline
- [x] Evaluate competing visions for AGI and articulate the neuro-symbolic argument

---

## Required Reading

- **Marcus, G. & Davis, E. (2019).** *Rebooting AI: Building Artificial Intelligence We Can Trust.* Pantheon Books. *(Sections relevant to Parts 1, 2, and 4)*
- **Kahneman, D. (2011).** *Thinking, Fast and Slow.* Farrar, Straus and Giroux. *(System 1 / System 2 framework)*

---

## References & Documentation

| Resource | Link |
|---|---|
| Wolfram Language Docs | https://reference.wolfram.com/language/ |
| WolframClient for Python | https://reference.wolfram.com/language/WolframClientForPython/ |
| PyTorch Docs | https://pytorch.org/docs/ |
| TensorFlow / Keras Docs | https://www.tensorflow.org/api_docs |
| LangChain Docs | https://python.langchain.com/docs/ |

---

*Module 10 · ITAI 4374 · Houston City College · Spring 2026*
*Author: Patricia McManus · Collaborator: Claude (Anthropic)*
