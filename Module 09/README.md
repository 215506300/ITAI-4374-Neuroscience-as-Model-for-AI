# ITAI 4374 — Module 09: World Models & Goal-Directed Behavior
**Course:** ITAI 4374 – Neuroscience and AI
**Institution:** Houston City College
**Instructor:** Prof. Patricia McManus
**Term:** Spring 2026


---

## Overview

This module explores one of the most powerful ideas shared by neuroscience and artificial intelligence: **world models**. Rather than simply reacting to events, intelligent systems — biological and artificial — build internal simulations of the world and use them to predict, plan, and pursue goals. Module 09 bridges the brain's predictive machinery to modern AI systems like DreamerV3, MuZero, and AlphaZero.

---

## Learning Objectives

By the end of this module, students will be able to:

1. Explain the **predictive brain** and how prediction errors drive learning
2. Describe Karl Friston's **Free Energy Principle** and its claim that all biological behavior minimizes surprise
3. Distinguish between the two strategies for reducing free energy: **perceiving** (updating beliefs) vs. **acting** (changing the world)
4. Define a **world model** and identify the brain regions that support internal simulation
5. Compare **model-based vs. model-free reinforcement learning**, including trade-offs
6. Describe how AI systems — **World Models (Ha & Schmidhuber), DreamerV3, and MuZero** — use learned world models to plan and act
7. Connect **goal-directed behavior** in the prefrontal cortex to hierarchical planning in AI agents

---

## Module Outline

### Part 1 — How the Brain Simulates the Future

| Section | Topic |
|---|---|
| 1 | Welcome — Where We Are in the Journey |
| 2 | The Predictive Brain — A World Inside Your Head |
| 3 | The Free Energy Principle — Minimizing Surprise |
| 4 | World Models — Your Brain's Internal Simulator |

**Key brain regions covered:**

| Brain Region | World Model Function | AI Equivalent |
|---|---|---|
| Hippocampus | Episodic simulation; mental time travel | Memory-augmented networks; experience replay |
| Cerebellum | Rapid forward models for motor control | Forward dynamics models; model-predictive control |
| Prefrontal Cortex | Abstract planning; holding goals in working memory | Monte Carlo Tree Search; hierarchical planners |
| Visual Cortex | Predictive coding; top-down predictions | Generative models (VAEs, diffusion models) |
| Basal Ganglia | Action selection; habit vs. goal-directed circuits | Actor-critic architectures in RL |

---

### Part 2 — World Models in Artificial Intelligence

| Section | Topic |
|---|---|
| 5 | From Neurons to Neural Networks — How AI Builds World Models |
| 6 | Model-Based vs. Model-Free Reinforcement Learning |
| 7 | Dreaming Machines — World Models in Action |

**AI systems covered:**
- **Ha & Schmidhuber World Models (2018)** — V-M-C architecture with dream-based training
- **AlphaGo / AlphaZero** — Monte Carlo Tree Search + learned world models
- **DreamerV3** — Latent-space imagination across 150+ tasks
- **MuZero** — Learning game rules entirely from experience

---

### Part 3 — Goal-Directed Behavior

| Section | Topic |
|---|---|
| 8 | Goals, Plans, and the Prefrontal Cortex |
| 9 | Active Inference — Acting to Confirm Your Model |
| 10 | The Future — World Models and the Road to AGI |

---

### Part 4 — Lab 09: Active Inference Maze Navigator

| Section | Topic |
|---|---|
| Lab | Active Inference Maze Navigator (Jupyter Notebook) |

---

## Lab 09: Active Inference Maze Navigator

Students implement a simple active inference agent that navigates a 5×5 grid maze by minimizing prediction error.

### What the lab covers:
- Implementing a **generative model** (the agent's internal map) using NumPy
- Writing a **Bayesian belief update** step (the perception/predictive coding loop)
- Implementing **action selection** that minimizes expected free energy
- Balancing **pragmatic value** (goal proximity) with **epistemic value** (curiosity/uncertainty reduction)
- Visualizing the agent's path and learned beliefs with Matplotlib

### Lab cells:
| Cell | Description |
|---|---|
| Cell 1 | Setup — import libraries, define the 5×5 maze |
| Cell 2 | Define the generative model — agent's prior beliefs |
| Cell 3 | Perception step — Bayesian belief update |
| Cell 4 | Action step — minimize expected free energy |
| Cell 5 | Run the active inference loop and visualize |

### Requirements

```
python >= 3.9
numpy
matplotlib
```

Install dependencies:

```bash
pip install numpy matplotlib
```

---

## Key Concepts

| Concept | Plain-Language Definition |
|---|---|
| **Predictive Coding** | The brain generates predictions and processes only the difference (error) between expectation and reality |
| **Free Energy Principle** | All biological systems minimize surprise by updating beliefs or acting to change the world |
| **Active Inference** | Acting to make the world match your internal model, rather than just reacting to it |
| **World Model** | An internal simulator that predicts future states so an agent can plan without acting |
| **Model-Based RL** | RL that builds an internal model before planning — more sample-efficient |
| **Model-Free RL** | RL from pure trial and error with no internal model — faster but requires more experience |
| **Goal-Directed Behavior** | Deliberate action guided by goals held in working memory (prefrontal cortex) |
| **Habitual Behavior** | Automatic, stimulus-driven action that does not require a conscious goal (basal ganglia) |
| **Intrinsic Motivation** | Curiosity driven by uncertainty reduction, not external reward |
| **JEPA** | Yann LeCun's Joint Embedding Predictive Architecture — proposed path to grounded AI world models |

---

## 📖 Required Reading

- Friston, K. (2010). *The free-energy principle: a unified brain theory?* Nature Reviews Neuroscience, 11(2), 127–138.
- Ha, D. & Schmidhuber, J. (2018). *World Models.* arXiv:1803.10122. → [https://worldmodels.github.io](https://worldmodels.github.io)

---

## Key Resources

| Resource | Link |
|---|---|
| World Models interactive demo | https://worldmodels.github.io |
| Yann LeCun — Path to Autonomous Machine Intelligence | https://openreview.net/pdf?id=BZ5a1r-kVsf |
| DeepMind MuZero blog | https://www.deepmind.com/blog/muzero-mastering-go-chess-shogi-and-atari-without-rules |
| PyMDP — Active Inference Toolbox | https://github.com/infer-actively/pymdp |
| Active Inference Institute | https://www.activeinference.org |
| Spinning Up in Deep RL (OpenAI) | https://spinningup.openai.com |
| Sutton & Barto — RL: An Introduction (free) | http://incompleteideas.net/book/the-book.html |

---

## Connection to Prior Modules

| Module | Connection |
|---|---|
| Module 02 | Prediction, world models, Thousand Brains Theory |
| Module 06 | Hippocampus and memory — now extended to future simulation |
| Module 07 | Attention is driven by prediction errors |
| Module 08 | Reward prediction error and RL — the foundation this module builds on |
| **Module 09** | **Simulating the future; goal-directed and active inference** |
| Module 10 | Neuro-Symbolic AI — adding structured reasoning to learned world models |

---

## Career Connections

| Role | Employer Examples | Tools |
|---|---|---|
| World Model Engineer | DeepMind, Meta AI | PyTorch, JAX, Dreamer |
| Simulation Engineer | Waymo, Tesla, NVIDIA | CARLA, Isaac Sim, Unreal Engine |
| RL Researcher | OpenAI, Google DeepMind | PyTorch, JAX |
| Robotics AI Engineer | Boston Dynamics, Figure AI, 1X Technologies | ROS, MuJoCo, Isaac |
| Cognitive AI Researcher | Academia, industry labs | Python, neuroscience methods |

---

*ITAI 4374 — Spring 2026 | Module 09 of 12*
