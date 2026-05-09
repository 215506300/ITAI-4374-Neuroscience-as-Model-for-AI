# ITAI 4374 — Module 06: Memory, Learning, and AI Architectures
**Course:** ITAI 4374 – Neuroscience and AI
**Institution:** Houston City College
**Instructor:** Prof. Patricia McManus
**Term:** Spring 2026

---

## Overview

Module 06 bridges neuroscience and artificial intelligence through the lens of **memory and learning**. Starting with the famous case of Henry Molaison (H.M.) — who lost the ability to form new memories after hippocampal surgery in 1953 — this module reveals that memory is not one thing but a collection of specialized systems. Each system has a distinct brain structure, computational purpose, and AI parallel.

---

## Learning Objectives

By the end of this module, you will be able to:

1. Explain the four biological memory systems and identify their brain structures
2. Describe hippocampal consolidation during sleep and its relevance to AI
3. Connect hippocampal replay to experience replay in Deep Reinforcement Learning
4. Compare AI memory architectures (LSTMs, Transformers, MANNs, RAG) to their biological inspirations
5. Articulate the biological plausibility debate around backpropagation
6. Evaluate which biological memory principles AI has adopted and which remain open challenges

---

## Part 1: How the Brain Remembers

### The Four Memory Systems

| System | Brain Region | What It Stores | AI Parallel |
|---|---|---|---|
| **Working** | Prefrontal Cortex | Temporary active info | Context window, RNN hidden state |
| **Episodic** | Hippocampus | Personal experiences (what, where, when) | RAG, replay buffers |
| **Semantic** | Cortex (distributed) | Facts and concepts | Trained model weights |
| **Procedural** | Basal Ganglia + Cerebellum | Skills and habits | RL policies, robot controllers |

> **Key insight:** Most AI systems have analogues to only 1–2 of these systems. The brain runs all four simultaneously.

### The Hippocampus — The Brain's Memory Engine

The hippocampus operates via the **trisynaptic circuit**:

```
Entorhinal Cortex → Dentate Gyrus → CA3 → CA1 → (back to Entorhinal Cortex)
```

- **Dentate Gyrus** — Pattern separation: makes similar inputs distinct
- **CA3** — Pattern completion: retrieves full memories from partial cues
- **CA1** — Novelty detection: is this new or familiar?

### Memory Consolidation & Sleep

The brain uses a **two-system architecture**:

- **Hippocampus**: Fast learning, limited capacity, temporary
- **Cortex**: Slow learning, vast capacity, permanent

During **slow-wave sleep**, the hippocampus replays recent experiences to the cortex — compressed and shuffled — gradually transferring memories to long-term storage.

| Sleep Stage | What It Consolidates | AI Parallel |
|---|---|---|
| Slow-Wave (Deep) | Facts, events, textbook material | Experience replay in DRL |
| REM (Dreaming) | Motor skills, emotions, creativity | Generative replay, data augmentation |

> Skipping sleep doesn't give you more study time — it erases what you already studied.

### Experience Replay: From Hippocampus to DeepMind

| Feature | Hippocampal Replay | DQN Experience Replay |
|---|---|---|
| When | During sleep | Between training steps |
| What | Recent waking experiences | (state, action, reward, next state) |
| Order | Compressed, shuffled | Random from buffer |
| Purpose | Consolidate, prevent forgetting | Stabilize training |
| Priority | Emotionally significant events | Prioritized by TD error |

Demis Hassabis (DeepMind CEO) studied hippocampal memory in his PhD, directly inspiring DQN (2013).

### Complementary Learning Systems (CLS)
*(McClelland, McNaughton & O'Reilly, 1995)*

Explains **catastrophic forgetting**: training a network on new data overwrites old knowledge. The brain's solution:

- Hippocampus rapidly encodes new experiences without disturbing cortical knowledge
- During sleep, replays experiences **interleaved** with old knowledge to the cortex
- Cortex learns gradually from the mixed stream → no catastrophic overwriting

---

## Part 2: How the Brain Learns

### Long-Term Potentiation (LTP)
*(Bliss & Lømo, 1973)*

Rapid, repeated stimulation → synaptic connection becomes **permanently stronger**.

- **NMDA receptor** = coincidence detector: only opens when BOTH neurons are active → Hebb's rule made real
- **AI parallel**: increasing a weight during training (positive gradient update)

### Long-Term Depression (LTD)

Slow, low-frequency stimulation → connection **weakens**.

- Together, LTP + LTD = a bidirectional volume knob for every connection
- **AI parallel**: decreasing a weight during training (negative gradient update)

> Key difference: AI uses a central algorithm to compute weight changes. The brain computes changes locally at each synapse.

### Neuromodulators — When to Learn

| Neuromodulator | Signal | Effect on Learning | AI Parallel |
|---|---|---|---|
| **Dopamine** | "That was surprising!" | Enhances LTP at active synapses when outcome > expected | Reward signal / TD error in RL |
| **Acetylcholine** | "Pay attention!" | Increases sensitivity to new input | Attention-gated learning |
| **Norepinephrine** | "Something important!" | Enhances memory across regions during arousal | Explore vs. exploit (ε-greedy) |

> **Key gap**: AI uses ONE fixed learning rate. The brain uses MULTIPLE dynamic rates simultaneously.

### Learning Speeds Across Systems

| System | Speed | Exposures Needed | Example |
|---|---|---|---|
| Episodic | Extremely fast (one-shot) | 1 | Food poisoning → never eat that again |
| Semantic | Slow | Many over weeks | Building up history knowledge |
| Procedural | Very slow | Thousands of reps | Months of daily piano practice |
| Working | Instant (but temporary) | 0 | Holding a phone number while dialing |

---

## Part 3: How AI Remembers

### AI Memory Architectures Compared

| Architecture | Memory Type | Capacity | Bio Parallel | Best For |
|---|---|---|---|---|
| RNN / LSTM | Internal (hidden state) | Small, fixed | Working memory (PFC) | Short sequences |
| Transformer | Internal (context window) | Medium, fixed | WM + attention | Text, code, reasoning |
| NTM / DNC | External (memory matrix) | Medium, flexible | Hippocampal R/W | Algorithmic tasks |
| RAG | External (database) | Very large | Hippocampal-cortical retrieval | Knowledge QA |
| Experience Replay | Buffer (FIFO) | Large | Hippocampal replay | Reinforcement learning |

### Transformers and Content-Addressable Memory

Transformer self-attention implements content-addressable memory — just like the hippocampus:

```
Query  →  "What am I looking for?"
Key    →  "What do I contain?"
Value  →  "What information do I provide?"

Attention(Q, K, V) = softmax(Q · Kᵀ / √d_k) · V
```

Partial cue (query) → retrieves stored patterns (key-value) based on similarity.

### RAG — The Modern Memory Solution

- **Model weights** = cortical semantic memory (general, slow-updated)
- **External database** = hippocampus (fast-updated, specific)
- **Query → retrieve → generate**

RAG is one of the most in-demand AI engineering skills today.

---

## Part 4: The Biological Plausibility Debate

### Why Backpropagation Is Biologically Implausible

| Problem | Description |
|---|---|
| Weight Transport | Backward pass needs exact copies of forward weights — no known bio mechanism |
| Non-local Error Signals | Neurons adjust based on output error many layers away; biology is LOCAL |
| Separate Phases | Brain activity is continuous and bidirectional — no neat two-phase computation |
| Precise Derivatives | Neurons use all-or-nothing spikes, not precise floating-point numbers |

### Hebbian Learning: "Fire Together, Wire Together"
*(Donald Hebb, 1949)*

- Two neurons active together → connection strengthens
- Out of sync → connection weakens
- ✓ Biologically plausible
- ✗ Cannot train deep networks (no error signal / credit assignment)

### Bio-Plausible Alternatives

| Algorithm | Weight Transport? | Global Error? | Separate Phases? | Performance vs. Backprop |
|---|---|---|---|---|
| Backpropagation | ✗ Yes | ✗ Yes | ✗ Yes | Gold standard |
| Hebbian / STDP | ✓ No | ✓ No | ✓ No | Limited |
| Feedback Alignment | ✓ No | Partial | Yes | ~95% |
| Predictive Coding | ✓ No | ✓ Local only | ✓ No | ~Equivalent |
| Forward-Forward | ✓ No | ✓ No | ✓ No | ~90% |

---

## Key Concepts & Terms

| Term | Definition |
|---|---|
| **LTP** | Long-Term Potentiation — synaptic strengthening via high-frequency stimulation |
| **LTD** | Long-Term Depression — synaptic weakening via low-frequency stimulation |
| **Catastrophic Forgetting** | Neural networks lose old knowledge when trained on new data |
| **CLS** | Complementary Learning Systems — hippocampus + cortex solve the fast/stable tradeoff |
| **Pattern Separation** | Dentate gyrus creates distinct representations for similar inputs |
| **Pattern Completion** | CA3 retrieves full memories from partial cues |
| **RAG** | Retrieval-Augmented Generation — combines model weights with external database |
| **NMDA Receptor** | Coincidence detector; molecular basis of Hebbian learning |
| **Predictive Coding** | Each layer predicts the layer below; errors propagate locally (≈ backprop) |
| **Place Cells** | Hippocampal neurons that fire at specific locations |
| **Grid Cells** | Entorhinal neurons firing in hexagonal patterns; coordinate system for space |

---

## The Big Picture: Biology → AI Status

| Biological Principle | Status in AI |
|---|---|
| Multiple memory systems | Partially adopted |
| Fast encoding + slow consolidation | Adopted (experience replay) |
| Content-addressable retrieval | Adopted (attention, RAG) |
| Pattern separation | Rarely used |
| Emotional tagging | Partial (prioritized replay) |
| Active forgetting | Emerging (EWC, pruning) |
| Dynamic learning rates (neuromodulators) | Mostly absent |
| Biologically plausible learning | Active research |

> **Biggest gap**: FLEXIBILITY — context-sensitive, emotionally modulated, continuously updating, reconstructive memory.

---

## Module 06 Key Takeaways

1. Memory is **four systems** with separate brain structures and AI parallels
2. The **two-system architecture** (hippocampus + cortex) solves the fast-learning vs. stable-storage tradeoff
3. **LTP/LTD + neuromodulators** = the brain's dynamic, context-dependent learning machinery
4. **Experience replay** is the clearest neuroscience → AI success story; sleep is part of learning
5. **Predictive coding** may let the brain do backprop-equivalent learning with local biology
6. The biggest gap: AI memory lacks **flexibility**, emotional modulation, and continuous updating

---

## References

- Bliss & Lømo (1973) — Discovery of LTP. *Journal of Physiology*
- McClelland, McNaughton & O'Reilly (1995) — CLS Theory. *Psychological Review*
- Mnih et al. (2015) — DQN. *Nature*
- Vaswani et al. (2017) — Attention Is All You Need. *NeurIPS*
- Graves et al. (2014/2016) — NTM / DNC. *arXiv / Nature*
- Banino et al. (2018) — Grid cells in AI agents. *Nature*
- Lillicrap et al. (2016) — Feedback Alignment. *Nature Communications*
- Hinton (2022) — Forward-Forward Algorithm. *arXiv*
- Tulving (1972) — Episodic and Semantic Memory
- Hebb (1949) — *The Organization of Behavior*
