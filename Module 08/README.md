# Module 08 — Decision Making: From Brain to Autonomous Systems
**Course:** ITAI 4374 – Neuroscience and AI
**Institution:** Houston City College
**Instructor:** Prof. Patricia McManus
**Term:** Spring 2026

---

## Overview

Module 08 bridges Part 1 of the course (the biology of the brain) with Part 2 (autonomous AI systems). It asks a single driving question:

> *"How does the brain choose what to do — and how do AI systems make decisions?"*

Students leaving this module understand decision-making as an **architecture**, not a single switch, and can map each brain structure to a parallel component in modern AI.

---

## Module Position in the Course Arc

| Module | Theme | Status |
|--------|-------|--------|
| 02 | COMPUTE — What does the brain compute? | ✓ Complete |
| 03 | BUILD — Brain anatomy and neurons | ✓ Complete |
| 04 | CONNECT — Spiking neural networks | ✓ Complete |
| 05 | SENSE — Sensory processing and perception | ✓ Complete |
| 06 | REMEMBER — Memory and learning | ✓ Complete |
| 07 | ATTEND AND AWARE — Attention and consciousness | ✓ Complete |
| **08** | **DECIDE — Decision making** | **◀ You are here** |
| 09 | IMAGINE — World models and goal-directed behavior | Up next |

---

## Learning Objectives

By the end of this module, students will be able to:

1. Identify the four brain regions in the decision circuit (PFC, Basal Ganglia, Amygdala, ACC) and explain what each contributes
2. Describe the Drift Diffusion Model and the speed-accuracy tradeoff
3. Explain dopamine's role as a reward prediction error signal and connect it to reinforcement learning
4. Distinguish System 1 (fast/automatic) from System 2 (slow/deliberate) thinking and identify AI parallels for each
5. Recognize common cognitive biases (anchoring, loss aversion, confirmation bias) and explain how they appear in AI systems
6. Trace the autonomous agent loop (Perceive → Reason → Decide → Act → Learn)
7. Evaluate real-world AI failures through the lens of reward hacking and the alignment problem

*Addresses SLOs: 1, 6*

---

## Folder Contents

```
module-08/
│
├── README.md                          ← You are here
│
├── slides/
│   └── ITAI_4374_Module_08_Decision_Making_Brain_and_Autonomous_systems.pdf
│
├── readings/
│   └── ITAI_4374_Module_08_Decision_Making_Brain__Systems.pdf
│
├── lab/
│   ├── lab_08_instructions.pdf        ← Lab prompt and rubric
│   ├── track_a_python/                ← Google Colab notebook (System 2 Agent)
│   └── track_b_wolfram/               ← Wolfram notebook (DDM + RL simulations)
│
└── assets/                            ← Images used in slides and readings
```

> **Note:** Add lab files to the `lab/` directory as they are released.

---

## Part 1 — The Brain's Decision System

### The Decision Circuit

No single brain region decides alone. Four structures form the core team:

| Region | Role | AI Parallel |
|--------|------|-------------|
| **Prefrontal Cortex (PFC)** | Plans, compares options, holds goals in working memory | Context window, value function, planner |
| **Basal Ganglia** | Selects which action is released; suppresses the rest (Go / No-Go) | Actor-critic reinforcement learning |
| **Amygdala** | Adds emotional and risk value to each option | Penalty signals, risk weighting |
| **Anterior Cingulate Cortex (ACC)** | Monitors for conflict and errors; signals when a task needs slower thinking | Confidence scoring, uncertainty estimation |

### Key Concepts — Part 1

- **Somatic Marker Hypothesis (Damasio):** Body-based emotional signals guide decisions before conscious reasoning catches up. Demonstrated by the Iowa Gambling Task.
- **Three Types of Decisions:** Perceptual (signal in noise), Value-based (costs vs. benefits), Social (modeling other minds).
- **Drift Diffusion Model:** Evidence accumulates as a noisy random walk toward a threshold. Explains both choice *and* response time. `dx = μ·dt + σ·dW`
- **Speed-Accuracy Tradeoff:** Lower threshold = faster but more errors. Higher threshold = slower but more accurate. The brain adjusts dynamically by context.
- **Dopamine as Teaching Signal:** Encodes *reward prediction error* — the difference between expected and actual outcomes. Not the "pleasure chemical."
  - Better than expected → dopamine spikes → repeat the action
  - As expected → no change → keep doing what works
  - Worse than expected → dopamine dips → try something different
- **Explore vs. Exploit:** Novelty and dopamine drive exploration; habits and basal ganglia circuits drive exploitation; PFC overrides both when stakes are high.
- **System 1 vs. System 2 (Kahneman):** Fast/automatic vs. slow/deliberate. The real danger is using System 1 when a situation demands System 2.

---

## Part 2 — From Brain to Autonomous Systems

### Brain → AI Mapping

| Brain Component | AI Component | Function |
|-----------------|-------------|---------|
| Dopamine (VTA/SNc) | TD error / reward signal | Signals better-or-worse-than-expected |
| Basal ganglia (striatum) | Policy / Q-values | Stores learned action preferences |
| Orbitofrontal cortex | Value function | Estimates expected future reward |
| Prefrontal cortex | Planner / MCTS | Simulates future states before acting |
| Hippocampus | Experience replay buffer | Replays past experiences for learning |

### Key Concepts — Part 2

- **Reinforcement Learning:** Observe → Act → Receive reward → Update policy. TD learning maps directly to dopamine RPE.
- **AlphaGo Architecture:** Policy network (basal ganglia) + Value network (OFC) + Monte Carlo Tree Search (PFC). Defeated Lee Sedol in 2016.
- **System 1 vs. System 2 in AI:**
  - System 1 → single forward pass (fast, fluent, may hallucinate)
  - System 2 → Chain-of-Thought, Tree of Thoughts, ReAct, self-reflection
- **The Autonomous Agent Loop:** Perceive → Reason → Decide → Act → Learn
- **When AI Decisions Go Wrong:** Amazon hiring tool (2018), COMPAS recidivism (2016), engagement-optimizing recommendation engines
- **The Alignment Problem / Goodhart's Law:** When a measure becomes a target, it stops being a good measure. AI needs engineered constraints because it lacks the social, emotional, and reputational pressures that constrain human decisions.
- **RLHF:** Collects human preferences → trains a reward model → fine-tunes the AI. Useful but inherits biases from feedback data.

---

## Cognitive Biases Quick Reference

| Bias | What It Does | AI Relevance |
|------|-------------|-------------|
| Anchoring | First number skews all estimates | Prompt engineering, pricing UX |
| Loss Aversion | Losses hurt ~2× more than equivalent gains | Notification design, nudge systems |
| Confirmation Bias | Seek evidence that confirms existing beliefs | Biased training data, filter bubbles |
| Availability Heuristic | Vivid examples feel more probable | Search ranking, risk models |
| Bandwagon Effect | Follow what others have chosen | Popularity-driven recommendations |
| Framing Effect | Presentation changes the decision | How AI explains options matters |
| Dunning-Kruger | Low skill → overconfidence | LLM hallucinations stated confidently |
| Sunk Cost Fallacy | Past investment drives future choices | AI does **not** have this (an advantage) |

---

## Lab Summary

### Track A — Python (Google Colab)
Build a **System 2 agent** using LangChain's Tree of Thoughts workflow.
- Agent faces a decision problem, generates multiple solution paths, evaluates each, and selects the best
- Compare performance with and without deliberative reasoning (System 1 vs. System 2 ablation)

### Track B — Wolfram
Simulate three decision-science models interactively:
1. **Drift Diffusion Model** — vary drift rate, noise, and threshold; observe effects on speed and accuracy
2. **Reward Prediction Error** — visualize Q-value convergence during RL training
3. **Iowa Gambling Task** — compare a rational agent vs. a somatic-marker-inspired agent

*Tools: Google Colab (free tier) · cloud.wolfram.com (free tier)*

---

## Discussion Questions

1. A GPS app recommends a route. What is its reward function? Where could it reward-hack?
2. A self-driving car faces two dangerous outcomes. Who defines the reward function, and who is responsible for the result?
3. Which brain advantage will AI close first — body-based emotional signals, theory of mind, or context-sensitive decision speed? Which will take the longest? Defend your answer.

---

## Bridge to Module 09

Module 08 treated decisions as isolated events. Module 09 asks:

> *"How does the brain imagine possible futures before choosing?"*

**Module 09: World Models and Goal-Directed Behavior**
Active Inference · Model-Based RL · Dreamer · MuZero

---

## Key References

| Source | Relevance |
|--------|-----------|
| Kahneman, D. (2011). *Thinking, Fast and Slow* | System 1 / System 2 framework |
| Schultz, Dayan & Montague (1997). *Science* | Dopamine as reward prediction error |
| Damasio, A. R. (1994). *Descartes' Error* | Somatic marker hypothesis |
| Sutton & Barto (2018). *Reinforcement Learning: An Introduction* | RL foundations |
| Silver et al. (2016). *Nature* | AlphaGo architecture |
| Wei et al. (2022). *NeurIPS* | Chain-of-Thought prompting |
| Yao et al. (2023). *NeurIPS* | Tree of Thoughts |

Full reference list: see `readings/ITAI_4374_Module_08_Decision_Making_Brain__Systems.pdf`, Section 16.

---

*ITAI 4374 · Houston City College · AI & Robotics Program · Patricia McManus · Spring 2026*
