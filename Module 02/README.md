# Module 02: Foundations & Models of the World
### *How the Brain Constructs Reality*
**Course:** ITAI 4374 – Neuroscience and AI
**Institution:** Houston City College
**Instructor:** Prof. Patricia McManus
**Term:** Spring 2026

---

## Learning Objectives

By the end of this module, students will be able to:

- Define neuroscience and identify its subfields most relevant to AI
- Explain why the brain constructs reality rather than passively receiving it
- Describe four major theories of how the brain builds a model of the world
- Connect neuroscience principles to current limitations and future directions in AI
- Identify and debunk common neuromyths that can lead to poor AI design decisions

---

## What is Neuroscience?

> **Textbook:** The scientific study of the brain, spinal cord, and neural networks throughout the body.
>
> **Practical:** Understanding how three pounds of biological tissue creates your entire experience of being alive.

### Brain Vital Stats

| Metric | Value |
|--------|-------|
| Neurons | ~86 billion |
| Synaptic Connections | ~100 trillion |
| Power Consumption | ~20 watts |
| % of Body's Energy | ~20% |
| Weight | ~1.4 kg |

### Subfields (Most Relevant for AI ⭐)

| Subfield | Focus | AI Relevance |
|----------|-------|-------------|
| ⭐ Computational Neuroscience | What algorithms does the brain run? | High |
| ⭐ Cognitive Neuroscience | Memory, attention, language, decisions | High |
| Systems Neuroscience | How neural circuits process information | Medium |
| Cellular Neuroscience | Individual neuron behavior | Low–Medium |
| Molecular Neuroscience | Genes, proteins, chemical signals | Low |
| Clinical Neuroscience | Brain disorders and treatments | Low |

---

## Why Study the Brain for AI?

### The Limitations Gap

| Capability | 🧠 Brain | 🤖 Current AI |
|------------|---------|--------------|
| Learning from few examples | ✅ | ❌ |
| Energy efficiency (20W vs MW) | ✅ | ❌ |
| Common sense reasoning | ✅ | ❌ |
| Continuous lifelong learning | ✅ | ❌ |
| Knowing what it doesn't know | ✅ | ❌ |

### The Brain as Proof of Concept
1. The brain achieves general intelligence
2. The brain is a physical system
3. If we understand the principles → we can implement them

> **Airplane Analogy:** We didn't copy birds feather-by-feather. But understanding *lift* was essential. We need the brain's *principles*, not its exact biology.

---

## The Brain's Model of the World

The brain doesn't passively receive reality like a camera — it actively **constructs** an internal simulation.

| What the Brain Receives | What the Brain Creates |
|------------------------|----------------------|
| Electrical spikes from sensory neurons | Objects, colors, sounds, meaning |
| No labels, no meaning attached | Spatial understanding and time |
| Just patterns of neural activity | Your unified conscious experience |

### The Inverse Problem (Helmholtz)
- **Forward Problem (Easy):** 3D scene → 2D image (what computer graphics does)
- **Inverse Problem (Hard):** 2D image → 3D scene (what perception must do — infinite solutions!)

---

## Four Theories of World Modeling

These theories are **complementary**, not competing — each illuminates a different aspect of brain function.

| Theory | Key Question | Status |
|--------|-------------|--------|
| Thousand Brains | How is knowledge structured? | Speculative but Actionable |
| Free Energy Principle | Why do brains predict? | Influential, Debated |
| Bayesian Brain | How does the brain handle uncertainty? | Well-Established |
| Global Workspace | How is information integrated? | Leading Theory |

---

### The Thousand Brains Theory *(Jeff Hawkins)*

- The **neocortex** contains ~150,000 cortical columns, each ~0.5mm wide with ~100,000 neurons
- Each cortical column builds its **own complete model** of the world using **reference frames**
- Columns collaborate through **voting** to reach a consensus perception
- The distributed setup explains the brain's resilience and flexibility

**Reference Frames:** The brain stores knowledge like GPS coordinates — a coffee cup's handle is positioned *relative* to its rim and base. Abstract ideas work the same way.

**Voting Process:**
1. Each column processes local input → generates candidate hypotheses
2. Columns communicate via lateral connections
3. They share votes for the best interpretation
4. The consensus becomes conscious perception

> *"Every cortical column builds its own model of the world."*

**AI Implication:** Neural networks lack explicit reference frames — this may explain why they struggle with viewpoint invariance and compositional generalization.

---

### Predictive Coding *(Jakob Hohwy)*

- The brain constantly **predicts** incoming sensory information
- Higher areas send **predictions down**; lower areas send **error signals up**
- Only the **mismatch** (prediction error) is transmitted — highly efficient
- The brain functions as a **prediction machine**

**Free Energy Principle (Karl Friston):** Organisms minimize the gap between predictions and reality by either:
- Updating internal beliefs *(perception)*
- Changing the environment *(action — "active inference")*

**AI Implication:** Parallels autoencoders, variational autoencoders, and possibly transformer attention mechanisms.

---

### The Bayesian Brain Hypothesis

The brain represents beliefs as **probabilities** and updates them using **Bayes' theorem**:

```
Posterior = (Likelihood × Prior) / Evidence
```

- **Prior:** What you believed before seeing evidence (evolutionary, developmental, contextual)
- **Likelihood:** How probable is this evidence given the hypothesis?
- **Posterior:** Updated belief after combining prior + evidence

**Example:** Hearing rustling → brain evaluates probability of wind vs. snake based on context.

**AI Implication:** Current AI often lacks structured priors, leading to overconfidence and poor generalization.

---

### Global Workspace Theory *(Bernard Baars)*

Using a **theater metaphor:**
- 🔦 **Spotlight** = Attention (what gets illuminated becomes conscious)
- 🎭 **Stage** = Global Workspace (limited-capacity conscious content)
- 👥 **Audience** = Unconscious specialized processors receiving the broadcast
- 🎬 **Backstage** = Executive processes directing the spotlight

When information wins the competition for workspace access → **global ignition** occurs (sudden, brain-wide broadcast).

**AI Implication:** Suggests consciousness-like systems may require a specific architecture: specialized processors feeding into a limited-capacity global broadcast mechanism.

---

## Neuromyths to Avoid

These are false — and believing them leads to poor AI design decisions:

| Myth | Reality | Why It Matters for AI |
|------|---------|----------------------|
| "We only use 10% of our brain" | All regions are active; 100% used over 24h | Don't design systems with assumed slack capacity |
| "Left brain = logical, right brain = creative" | Both hemispheres collaborate on virtually everything | Don't over-compartmentalize AI modules |
| "Learning styles" (visual/auditory/kinesthetic) | Thoroughly debunked; no evidence | Don't build AI tutors around nonexistent categories |
| "Brain is hard-wired by adulthood" | Neuroplasticity continues throughout life | Don't underestimate continual learning |
| "Bigger brain = smarter" | Einstein's brain was average size | Model size ≠ intelligence |

---

## AI Takeaways & Implications

| Brain Principle | Current AI Gap | Promising Direction |
|-----------------|---------------|---------------------|
| World Models | Implicit/emergent only | DreamerV3, JEPA (LeCun) |
| Reference Frames | Viewpoint-dependent | Capsule Networks, Geometric DL |
| Prediction | Feed-forward dominant | PredNet, Predictive Coding Nets |
| Uncertainty | Often overconfident | Bayesian Deep Learning, MC Dropout |
| Global Workspace | No attention bottleneck | Workspace-style architectures |
| Continual Learning | Catastrophic forgetting | Brain-inspired memory consolidation |
| Active Inference | Passive perception | PyMDP framework |

---

## Lab: Cortical Column Simulation

Simulate the **voting mechanism** from the Thousand Brains Theory.

**Platform:** Python (NumPy) or Wolfram Mathematica

**What You'll Build:**
- Multiple "columns" each receiving partial sensory input
- Each column maintains candidate object hypotheses
- A voting mechanism for columns to reach consensus
- Visualization of consensus emerging over time

**Algorithm Overview:**
1. Initialize N columns, each with a different patch of input
2. Each column generates initial hypotheses from local input
3. Columns share votes with neighbors (simulating lateral connections)
4. Each column updates beliefs based on received votes
5. Repeat until consensus or max iterations reached
6. Output: winning hypothesis + confidence level

**Learning Goals:**
- Understand how distributed representations combine through voting
- Experience the speed/accuracy trade-off in consensus mechanisms
- Connect abstract theory to concrete implementation
- Identify limitations of simplified models

> Starter code available on Canvas under **Module 02 Lab Materials**. Estimated time: 2–3 hours.

---

## Key Takeaways

- The brain is **proof** that general intelligence is achievable in a physical system
- World models are **central to cognition** — the brain constructs reality, it doesn't just receive it
- Multiple neuroscience theories offer **complementary insights** for AI design
- Accurate brain knowledge leads to **better engineering decisions**
- The Thousand Brains Theory provides a concrete blueprint for **distributed, robust AI architectures**

---

## Resources & Further Reading

| Resource | Type | Link |
|----------|------|------|
| *A Thousand Brains* — Jeff Hawkins | Book | ISBN: 978-1541675810 |
| *Being You* — Anil Seth | Book | ISBN: 978-0525562641 |
| *The Brain: The Story of You* — David Eagleman | Book | ISBN: 978-0307950604 |
| Numenta Research Papers & Code | Website | numenta.com |
| HTM School | YouTube Series | Search "HTM School" |
| PyMDP — Active Inference | GitHub | github.com/infer-actively/pymdp |
| DreamerV3 — World Models for RL | GitHub | github.com/danijar/dreamerv3 |
| BrainFacts.org | Education | brainfacts.org |

### Key Papers
- Hawkins et al. (2019). *A Framework for Intelligence and Cortical Function.* Frontiers in Neural Circuits.
- Friston, K. (2010). *The free-energy principle: a unified brain theory?* Nature Reviews Neuroscience.
- Rao & Ballard (1999). *Predictive coding in the visual cortex.* Nature Neuroscience.
- Knill & Pouget (2004). *The Bayesian brain.* Trends in Neurosciences.
- Dehaene, S. (2014). *Consciousness and the Brain.* Viking.

