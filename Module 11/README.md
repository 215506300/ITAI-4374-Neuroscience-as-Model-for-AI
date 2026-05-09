# ITAI 4374 — Neuroscience as a Model for AI
## Module 11: Embodied Cognition and Robotics

> *Can intelligence exist without a body?*

**Houston City College | AI & Robotics Program | 2026**

---

## 📁 Folder Contents

| File | Description |
|------|-------------|
| `ITAI_4374_Module_11_Embodied_Cognition_and_Robotics.pdf` | Full reading — 40-page course document with all sections, figures, knowledge checks, glossary, and references |
| `ITAI_4374_Module_11_Embodied_Cognition.pdf` | Slide deck — 28-slide lecture presentation |

---

## 🧠 Module Overview

Module 11 shifts focus from brain-only intelligence to the full organism. After ten modules studying neural computation in relative isolation, this module adds the body — and examines how physical embodiment changes everything about how intelligence works and how AI systems are designed.

The module is divided into two parts:

**Part 1 — The Biology of Embodied Intelligence**
What the body contributes to thought, movement, and learning

**Part 2 — Embodied AI: Intelligence in the Physical World**
Affordances, sim-to-real, neuromorphic control, and career frontiers

---

## 📚 What You Will Learn

- The theory of **embodied cognition** and why the body is not just input/output hardware
- How the **cerebellum** operates as the brain's predictive motor controller (the predict-act-correct loop)
- **Proprioception** and **interoception** — the hidden sensory systems that give organisms their sense of self
- The **perception-action loop** and efference copies
- **Mirror neurons** and their AI equivalent: imitation learning (behavioral cloning, IRL, LfD)
- **Predictive motor control** — forward and inverse models, phantom limb pain, and Model Predictive Control in robotics
- What changes when AI gets a body: affordances, morphological computation, and the sim-to-real gap
- **Neuromorphic motor control** and soft robotics
- **Foundation models for robotics**: Vision-Language-Action (VLA) models, RT-2, and NVIDIA Isaac GR00T N
- The **Embodied Turing Test** (Zador et al., 2023) and why current robotic AI still falls short

---

## 🔑 Key Concepts at a Glance

| Concept | One-Line Definition |
|---|---|
| Embodied Cognition | Intelligence is a property of an organism acting in a world, not just neural computation |
| Cerebellum | 10% of brain volume, ~80% of neurons; runs the predict-act-correct loop for movement |
| Proprioception | The continuous, unconscious sense of body position and movement in space |
| Interoception | The sense of the body's internal physiological state (heart rate, hunger, temperature) |
| Efference Copy | A copy of a motor command sent to sensory areas to predict and cancel self-generated motion |
| Affordance | The action possibilities an object or environment offers to an agent with specific physical capabilities (Gibson, 1979) |
| Morphological Computation | Physical body structure performs computational work without neural processing |
| Sim-to-Real Gap | Performance degradation when a policy trained in simulation is deployed on real hardware |
| Behavioral Cloning | Imitation learning by directly copying observed actions |
| Inverse Reinforcement Learning | Inferring the goal behind demonstrated behavior, then pursuing it independently |
| VLA Model | Vision-Language-Action model — sees, understands language, and outputs motor commands in one unified model |
| Isaac GR00T N | NVIDIA's open-source VLA foundation model for robots; released GTC 2026 |
| Embodied Turing Test | Benchmark: can an AI navigate and manipulate the physical world as well as a mouse or rat? |

---

## 🧪 Lab Assignments

### Python Lab — Simulated Robotic Reaching (Gymnasium)
- **Environment:** `Gymnasium Reacher-v4` (2-joint robot arm, CPU-compatible)
- **Objective:** Compare a **reactive controller** (responds to current position error) against a **predictive controller** (uses a forward model)
- **Tools:** Google Colab (free tier), Gymnasium, NumPy
- **Setup:** Runtime → Change runtime type → T4 GPU (or CPU fallback)
- Starter notebook provided by instructor

### Wolfram Assignment — Simulating a Forward Motor Model
- **Platform:** `cloud.wolfram.com` (no installation required)
- **Objective:** Model the cerebellum's predict-act-correct cycle
- **Tasks:**
  1. Build a forward model of a one-joint limb
  2. Introduce a perturbation (sudden external load) and observe the prediction error signal
  3. Model the correction update and convergence
  4. Visualize the prediction-error-correction cycle and connect it to the cerebellar loop
- Base Wolfram notebook provided by instructor

---

## 🔗 Course Connection

| Module | Topic | Connection to Module 11 |
|--------|-------|--------------------------|
| Module 02 | World Models | Predictive processing framework extended to physical action |
| Module 03 | Brain Anatomy | Cerebellum and basal ganglia revisited in motor context |
| Module 04 | Spiking Neurons | Neuromorphic chips for real-time motor control |
| Module 05 | Sensory Systems | Proprioception and interoception as sensory modalities |
| Module 08 | Decision-Making | Basal ganglia (WHAT) vs. cerebellum (HOW) |
| Module 09 | Goal-Directed Behavior | World models extended to physical robotic control |
| Module 10 | Neuro-Symbolic Reasoning | Embodiment as the missing layer |

---

## 💼 Career Pathways

- **Robotics AI Engineer** — perception, control, and learning systems for physical robots
- **Human-Robot Interaction (HRI) Specialist** — safe and natural human-robot collaboration
- **Simulation Engineer** — building and maintaining training environments for robot policies
- **Neuromorphic Systems Engineer** — real-time robotic sensing and control on neuromorphic hardware
- **Warehouse Automation Specialist** — deployment and maintenance of embodied AI in fulfillment centers
- **Surgical Robotics Integration Specialist** — robotic surgical systems in clinical environments

---

## 📖 Key References

- Brooks, R. A. (1991). Intelligence without representation. *Artificial Intelligence, 47*(1-3), 139–159.
- Gibson, J. J. (1979). *The Ecological Approach to Visual Perception.* Houghton Mifflin.
- Gallese, V., Fadiga, L., Fogassi, L., & Rizzolatti, G. (1996). Action recognition in the premotor cortex. *Brain, 119*(2), 593–609.
- Wolpert, D. M., & Kawato, M. (1998). Multiple paired forward and inverse models for motor control. *Neural Networks, 11*(7-8), 1317–1329.
- Brohan, A., et al. (2023). RT-2: Vision-language-action models transfer web knowledge to robotic control. *arXiv:2307.15818.*
- Zador, A., et al. (2023). Catalyzing next-generation artificial intelligence through NeuroAI. *Nature Communications, 14,* 1597.
- NVIDIA Corporation. (2026, March 18). NVIDIA and global robotics leaders take physical AI to the real world. *NVIDIA Newsroom.*
  
---

*ITAI 4374: Neuroscience as a Model for AI | Houston City College | AI & Robotics Program | 2026*
