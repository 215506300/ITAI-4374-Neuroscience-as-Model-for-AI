# Module 06 — Memory, Learning, and AI Architectures
### ITAI 4374: Neuroscience as a Model for AI
**Houston City College · AI & Robotics Program · Professor Patricia McManus**

> *"Memory is not one thing — it is a collection of separate systems."*
> — Lesson of Henry Molaison (H.M.), 1926–2008

---

## 📁 Folder Contents

| File | Description |
|------|-------------|
| `ITAI_4374_Module_06__Memory_and_learning.pdf` | Slide deck — lecture presentation (37 slides) |
| `ITAI_4374_Module_06_Booklet_Memory__Learning.pdf` | Full reading booklet (56 pages) |
| `README.md` | This file |

---

## 🧭 Where This Module Fits

```
Module 04 (Neurons & Spiking)
    ↓
Module 05 (Sensory Processing)
    ↓
Module 06 (Memory & Learning)   ← YOU ARE HERE
    ↓
Module 07 (Attention & Consciousness)
    ↓
Module 08 (Decision Making)
```

---

## 🎯 Learning Objectives

By the end of this module you will be able to:

1. Explain the **four biological memory systems** and identify their brain structures
2. Describe how the **hippocampus consolidates memories during sleep** — and why it matters for AI
3. Explain **LTP, LTD, and neuromodulators** as the cellular machinery of learning
4. Connect **hippocampal replay** to experience replay in Deep Reinforcement Learning
5. Compare **AI memory architectures** to their biological inspirations
6. Articulate the **biological plausibility debate** around backpropagation

---

## 🧠 Part 1 — How the Brain Remembers

### The Four Memory Systems

| System | What It Stores | Brain Region | AI Parallel |
|--------|---------------|--------------|-------------|
| **Working** | Current task info (temporary) | Prefrontal Cortex | Context window, RNN hidden state |
| **Episodic** | Personal experiences (what/where/when) | Hippocampus | RAG, replay buffers |
| **Semantic** | Facts & concepts (context-free) | Cortex (distributed) | Trained model weights |
| **Procedural** | Skills & habits (largely unconscious) | Basal Ganglia + Cerebellum | RL policies, robot controllers |

> **Key insight:** Most AI systems have analogues to only 1–2 of these. The brain runs all four simultaneously.

---

### The Hippocampus — Memory Engine

The hippocampus uses a **trisynaptic circuit**:

```
Entorhinal Cortex → Dentate Gyrus → CA3 → CA1
        ↑                                    ↓
        └────────────────────────────────────┘
```

- **Dentate Gyrus** → Pattern separation (making similar inputs distinct)
- **CA3** → Pattern completion (retrieving full memory from partial cue)
- **CA1** → Novelty detection (new vs. familiar?)

---

### Memory Consolidation & Sleep

The brain uses a **two-system architecture**:

```
HIPPOCAMPUS (fast, limited, temporary)
      │
      │  replay during slow-wave sleep
      ▼
CORTEX (slow, vast, permanent)
```

- **Slow-Wave Sleep** → Hippocampal replay → consolidates facts & events → analogous to **experience replay in DRL**
- **REM Sleep** → Motor skills, emotions, creativity → analogous to **generative replay / data augmentation**

> ⚠️ Skipping sleep doesn't give you more study time — it erases what you already studied.

---

### Experience Replay: Hippocampus → DeepMind

| Feature | Hippocampal Replay | DQN Experience Replay |
|---------|-------------------|----------------------|
| When | During sleep | Between actions |
| What | Recent waking experiences | (state, action, reward, next state) |
| Order | Compressed, shuffled | Random from buffer |
| Purpose | Consolidate; prevent forgetting | Stabilize training |
| Priority | Emotional/surprising events | Prioritized by TD error |

> Demis Hassabis (DeepMind CEO) studied hippocampal memory for his PhD → directly inspired DQN (2013).

---

## ⚗️ Part 2 — How the Brain Learns

### LTP & LTD — The Volume Knob

| Mechanism | Trigger | Effect | AI Parallel |
|-----------|---------|--------|-------------|
| **LTP** (Long-Term Potentiation) | High-frequency stimulation | Strengthens connection | Increase weight |
| **LTD** (Long-Term Depression) | Low-frequency stimulation | Weakens connection | Decrease weight |

- **NMDA receptor** = coincidence detector → opens only when BOTH neurons are active → Hebb's rule made real
- Together, LTP + LTD = **bidirectional volume knob** for every connection

### Neuromodulators — When to Learn

| Neuromodulator | Signal | Effect on Learning | AI Parallel |
|----------------|--------|--------------------|-------------|
| **Dopamine** | "That was surprising!" | Enhances LTP at active synapses | TD error / reward signal in RL |
| **Acetylcholine** | "Pay attention!" | Turns up sensitivity to new input | Attention-gated learning |
| **Norepinephrine** | "Something important!" | Enhances memory across regions | ε-greedy exploration |

> **Key gap:** AI uses ONE fixed learning rate. The brain uses MULTIPLE dynamic rates simultaneously.

---

## 🤖 Part 3 — How AI Remembers

### AI Memory Architecture Comparison

| Architecture | Memory Type | Capacity | Bio Parallel | Best For |
|-------------|-------------|----------|--------------|----------|
| RNN / LSTM | Internal (hidden state) | Small, fixed | Working memory | Short sequences |
| Transformer | Internal (context) | Medium, fixed | WM + attention | Text, code, reasoning |
| NTM / DNC | External (matrix) | Medium, flexible | Hippocampal R/W | Algorithmic tasks |
| RAG | External (database) | Very large | Hippo-cortical | Knowledge QA |
| Experience Replay | Buffer (FIFO) | Large | Hippocampal replay | Reinforcement learning |

### LSTM Gates

```
Input Gate  → what to store
Forget Gate → what to discard
Output Gate → what to use now
Cell State  → protected highway (information persists across time)
```

### Transformer Self-Attention

```
Query: "What am I looking for?"
Key:   "What do I contain?"
Value: "What information do I provide?"

Attention(Q, K, V) = softmax(Q · Kᵀ / √d_k) · V
```

> This IS content-addressable memory — just like the hippocampus. Partial cue (query) → retrieves stored patterns (key-value) based on similarity.

---

## 🔬 Part 4 — The Biological Plausibility Debate

### Why Backprop Is Biologically Implausible

| Problem | Description |
|---------|-------------|
| **Weight Transport** | Backward pass needs exact copies of forward weights — no known bio mechanism |
| **Non-local Error Signals** | Deep neurons adjust based on output error — but biology is LOCAL |
| **Separate Phases** | Brain activity is continuous/bidirectional — no neat two-phase computation |
| **Precise Derivatives** | Neurons use all-or-nothing spikes — not floating-point numbers |

### Bio-Plausible Alternatives

| Algorithm | Weight Transport? | Global Error? | Separate Phases? | vs. Backprop |
|-----------|:---:|:---:|:---:|:---:|
| Backpropagation | ✗ | ✗ | ✗ | Gold standard |
| Hebbian / STDP | ✓ | ✓ | ✓ | Limited |
| Feedback Alignment | ✓ | Partial | ✗ | ~95% |
| Predictive Coding | ✓ | ✓ (local) | ✓ | ~Equivalent |
| Forward-Forward | ✓ | ✓ | ✓ | ~90% |

---

## 📊 What Biology Has (and AI Mostly Lacks)

| Biological Principle | Status in AI |
|---------------------|-------------|
| Multiple memory systems | Partially adopted |
| Fast encoding + slow consolidation | Adopted (experience replay) |
| Content-addressable retrieval | Adopted (attention, RAG) |
| Emotional tagging | Partial (prioritized replay) |
| Dynamic learning rates (neuromodulators) | Mostly absent |
| Active forgetting | Emerging (EWC, pruning) |
| Biologically plausible learning | Active research |

> **Biggest gap:** FLEXIBILITY — context-sensitive, emotionally modulated, continuously updating, reconstructive memory.

---

## 📚 Key Terms

`LTP` · `LTD` · `Episodic Memory` · `Semantic Memory` · `Procedural Memory` · `Working Memory` · `Hippocampus` · `Trisynaptic Circuit` · `Pattern Separation` · `Pattern Completion` · `Memory Consolidation` · `Slow-Wave Sleep` · `REM Sleep` · `Experience Replay` · `Complementary Learning Systems (CLS)` · `Catastrophic Forgetting` · `LSTM` · `Transformer` · `Self-Attention` · `RAG` · `Neural Turing Machine` · `Hebbian Learning` · `STDP` · `Backpropagation` · `Predictive Coding` · `Feedback Alignment` · `Dopamine` · `Acetylcholine` · `Norepinephrine` · `Place Cells` · `Grid Cells`

---

## 🔗 Key References

- Bliss & Lømo (1973) — Discovery of LTP
- McClelland, McNaughton & O'Reilly (1995) — Complementary Learning Systems
- Hochreiter & Schmidhuber (1997) — LSTM
- Mnih et al. (2015) — DQN / Experience Replay *(Nature)*
- Vaswani et al. (2017) — Attention Is All You Need
- Banino et al. (2018) — Grid cells emerge in AI navigation agents *(Nature)*
- Lillicrap et al. (2016) — Feedback Alignment
- Hinton (2022) — Forward-Forward Algorithm

---

## ➡️ Next: Module 07 — Attention & Consciousness in AI

> *How does the brain DECIDE what to focus on? Does AI need consciousness to be truly intelligent?*

---
*ITAI 4374 · Houston City College · AI & Robotics Program*
