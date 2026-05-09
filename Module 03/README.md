# Module 3 — Brain Anatomy & Computational Neuroscience

---

## Course Materials

### ITAI_4374_Module_03_Booklet.pdf
**Author:** Patricia McManus — *Student Booklet, Restructured Edition*

The primary module booklet, divided into two parts:

**Part 1 — The Brain (No Math Required)**
- Brain overview: scale, anatomy, and the three major divisions (hindbrain, midbrain, forebrain)
- The four lobes of the cerebral cortex and their functions, including the visual processing hierarchy that inspired CNNs
- Key subcortical structures: thalamus (routing), hippocampus (memory), amygdala (emotion), and basal ganglia (action selection/reinforcement learning)
- Neuron anatomy: dendrites, soma, axon, and synapse — with direct AI analogies for each
- Action potentials: the all-or-nothing spike, resting potential, threshold, and refractory period

**Part 2 — Computational Neuroscience (Math Included)**
- What computational neuroscience is and David Marr's three levels of analysis (computational, algorithmic, implementational)
- The Leaky Integrate-and-Fire (LIF) neuron model — equation explained step by step using the "leaky bucket" analogy
- Worked numerical example walking through the LIF equation
- Neural coding strategies: rate coding, temporal coding, and population coding — with connections to ANNs, SNNs, and transformer embeddings
- Lab prep: implementing a LIF neuron simulation in Python or Wolfram Language

---

## Supplemental Readings

### A03_Maira_Tanweer_ITAI4374.pdf
**Author:** Maira Tanweer Chachar — Houston City College (02/05/2026)
**Title:** *Bridging Neuroscience and Artificial Intelligence*

A student paper covering three areas:

- **Neural Network Comparison Analysis** — structural comparison of biological and artificial neurons, with a summary table mapping dendrites → input features, soma → activation function, axon → layer output, and synapse → learned weights
- **Brain Architecture and AI Design** — how the brain's hierarchical visual processing parallels CNNs, how RNNs/LSTMs mirror hippocampal memory, and how attention mechanisms relate to biological selective attention
- **Amygdala and Emotion Processing** — the amygdala's role in fear and risk evaluation and how emotion-inspired AI could improve human-AI interaction and autonomous decision-making
- **Integration Analysis** — future directions including neuromorphic computing, spiking neural networks, and the energy efficiency gap between biological brains (~20 watts) and large AI models

---

### blog_wolfram_com-Brain_Neurons_Cognition_Computational_Neuroscience.pdf
**Source:** Wolfram Research Blog (June 6, 2017)
**Title:** *Brain, Neurons, Cognition: Computational Neuroscience*

A computational walkthrough of neuroscience data using the Wolfram Language, covering:

- **Brain Anatomy & Network** — visualizing the amygdala in 3D, mapping its outgoing connections, identifying feedback loops, and tracing the amygdala–prefrontal cortex circuit
- **Neuron Characteristics** — querying electrophysiological properties of specific neuron types (e.g., hippocampus CA1 pyramidal cells), comparing spike amplitudes across neuron types, and simulating spike propagation with the Hodgkin-Huxley and Izhikevich models
- **Cognitive Map** — using fMRI-based statistical maps to visualize brain activity during visual perception, language processing, and emotion; hierarchical organization of cognitive functions by lobe

---

### medium_com-A_Brief_Introduction_to_Computational_Neuroscience.pdf
**Author:** Osheen Jain — *Medium* (November 1, 2022)
**Title:** *A Brief Introduction to Computational Neuroscience*

A concise accessible overview of the field, covering:

- What computational neuroscience is: the intersection of neuroscience, computer science, and mathematics
- Key research questions: how neurons compute, how memory is stored and retrieved, neural mechanisms of perception and consciousness
- Why combining computation and neuroscience matters: the brain's complexity, its role in all cognition, and its constant adaptation to experience
- Real-world applications: brain-machine interfaces (BMIs), treatments for neurological disorders (Alzheimer's, Parkinson's), and prosthetic devices

---

## How the Materials Fit Together

| Topic | Booklet | Student Paper | Wolfram Blog | Medium Article |
|---|---|---|---|---|
| Neuron anatomy & signaling | Sections 4–5 | Neural Network Comparison | Neuron Characteristics | Introduction |
| Brain regions & functions | Sections 2–3 | Brain Architecture | Brain Anatomy & Network | Research Fields |
| Biological vs. artificial neurons | Section 9 | Comparison Table | — | Why Combine? |
| Computational modeling | Sections 6–8 | — | Hodgkin-Huxley / Spike Simulation | Goals of CompNeuro |
| AI applications | Section 9 | Integration Analysis | Cognitive Map / fMRI | BMIs & Disorders |

*The booklet provides the foundational framework. The supplemental readings extend it with a student synthesis, hands-on computational examples, and a field-level introduction.*
