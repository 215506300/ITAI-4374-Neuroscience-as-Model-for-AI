# Module 04 — Neurons & Spiking Neural Networks  
ITAI 4374 — Neuroscience as a Model for AI  
Houston City College · Spring 2026

---

## 1. Overview
This module introduces the third generation of neural networks—Spiking Neural Networks (SNNs). Students extend the single-neuron LIF model from Module 03 into multi-neuron systems, explore spike-based encoding, and implement spiking simulations using Python and Wolfram Language. The module also connects SNNs to neuromorphic hardware such as Intel Loihi 2 and event‑driven sensors.

---

## 2. Learning Objectives
By the end of this module, students will be able to:

- Implement LIF neurons and multi‑neuron spiking networks.
- Encode data using rate, latency, and delta-modulation spike coding.
- Train SNNs using surrogate gradients and ANN‑to‑SNN conversion.
- Analyze firing‑rate curves, spike timing, and temporal computation.
- Explain neuromorphic hardware constraints and advantages.
- Build interactive dashboards (Wolfram) and simulations (Python).

---

## 3. Key Concepts

### 3.1 Three Generations of Neural Networks
- **1st Gen:** Binary threshold units (McCulloch–Pitts)
- **2nd Gen:** Continuous activations (ReLU, sigmoid)
- **3rd Gen:** Spiking neurons with temporal dynamics

### 3.2 Why Spikes Matter
- Event‑driven computation  
- Sparse activation → energy efficiency  
- Temporal coding → natural sequence processing  
- Ultra‑low latency  
- Biological plausibility  

### 3.3 LIF Neuron Model
- Integrate input  
- Leak toward rest  
- Fire when threshold crossed  
- Reset after spike  

### 3.4 Encoding Methods
- **Rate coding:** spike frequency ∝ intensity  
- **Latency coding:** spike time ∝ intensity  
- **Delta modulation:** spikes only on change  
- **Direct input:** continuous → spiking via neuron dynamics  

### 3.5 Training SNNs
- Surrogate gradient descent  
- ANN‑to‑SNN conversion  
- STDP / R‑STDP  

### 3.6 Neuromorphic Hardware
- Intel Loihi 2  
- IBM TrueNorth  
- Event‑driven cameras (DVS)  
- Hala Point (1.15B neurons)  

---

## 4. Required Work

### 4.1 Python Lab (Google Colab)
Students must complete:

- LIF neuron simulation  
- Spike raster plots  
- Rate & temporal encoding  
- Mini SNN with synaptic weights  
- f‑I curve generation  
- Experiments (threshold, tau, noise, frequency, etc.)  
- Final reflection  

### 4.2 Wolfram Assignment
Students must complete:

- NDSolve LIF simulation  
- WhenEvent spike reset  
- Manipulate[] interactive dashboard  
- f‑I curve  
- Sine‑wave encoding  
- Experiments (threshold, tau, refractory period, etc.)  
- Final reflection  

---

## 5. Deliverables

### Python Notebook
`L04_FirstName_LastName_ITAI4374.ipynb`

### Wolfram Notebook or PDF
`A04_FirstName_LastName_ITAI4374.nb`  
or  
`A04_FirstName_LastName_ITAI4374.pdf`

---

## 6. Folder Structure

