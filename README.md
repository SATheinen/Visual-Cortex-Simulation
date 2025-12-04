# Visual Cortex Simulation: Neural Population Decoding

[![Thesis](https://img.shields.io/badge/Thesis-PDF-blue)](Masterarbeit_final.pdf)
[![Python](https://img.shields.io/badge/Python-3.8+-green.svg)](https://www.python.org/)
[![NEST](https://img.shields.io/badge/Simulator-NEST-orange.svg)](https://www.nest-simulator.org/)

> Large-scale computational model of visual cortex layer 4 (macaque V1) investigating how neural populations decode visual orientation from noisy spatiotemporal activity.

![Spatiotemporal Activity](https://github.com/user-attachments/assets/4621f4d8-24ea-4be4-8c88-06da8ebe0d7c)

---

## 🧠 What This Project Does

Built a biologically-constrained 1M-neuron spiking neural network to understand how the brain processes visual information. The model:

- **Processes visual stimuli** (gratings, bars) through simulated retina → thalamus → cortex pathway
- **Exhibits emergent dynamics** including spatiotemporal spiking waves and population-level synchronization
- **Decodes orientation** from noisy neural population activity with high robustness
- **Achieves biological realism** using connectivity patterns from experimental neuroscience literature

**Key Challenge Solved:** How do large neural populations reliably extract information (visual orientation) from noisy, high-dimensional spatiotemporal signals?

---

## 📊 Results Visualization

**Above animation shows:**
- **Top row:** Population firing rates across 16mm² cortical patch (1ms temporal resolution)  
- **Middle row:** Thalamic input patterns from retina model  
- **Bottom row:** Individual neuron spike trains showing coordinated activity

**What you're seeing:** Emergent traveling waves of neural activity as the network processes a moving visual stimulus—demonstrating how local neural interactions produce coordinated population responses.

---

## 🔬 Technical Highlights

### Scale
- **1,000,000 neurons** across 4 cortical layers
- **1,000,000,000+ synapses** with biologically realistic connectivity
- **20,000,000,000+ datapoints** processed (0.1ms resolution, 20s simulations)
- **16mm² cortical area** (equivalent to central visual field representation)

### Architecture
- **Leaky Integrate-and-Fire neurons** (conductance-based)
- **Exponentially decaying spatial connectivity** (distance-dependent)
- **Orientation-specific connectivity patterns** (patchy long-range, push-pull short-range)
- **Realistic synaptic delays** (distance + conduction velocity)

### Input Model
- **Retina preprocessing** using center-surround receptive fields (Mexican hat filters)
- **ON/OFF pathways** mimicking biological thalamic separation
- **Gabor-based thalamocortical projections** creating orientation selectivity
- **Visual stimuli:** Moving gratings, bars, and dashed patterns

### Key Innovation
**No backpropagation or gradient descent** — network learns topology through biologically-plausible Hebbian-inspired connectivity rules, demonstrating that biological constraints alone can produce robust computation.

---

## 🎯 Applications & Relevance

This work is directly relevant to:

- **Brain-Computer Interfaces (BCIs):** Understanding population-level neural coding for visual decoding
- **Neuromorphic Computing:** Biologically-inspired architectures for edge AI
- **Computational Neuroscience:** Testing theories of cortical processing
- **Medical Applications:** Understanding visual processing disorders

**Why it matters:** Real brains process information with noisy, sparse, asynchronous spiking. This model shows how robust computation emerges from biological constraints—principles applicable to EEG decoding, neuromorphic hardware, and explainable AI.

---

## 💻 Technical Stack

- **Simulator:** [NEST Neural Simulation Tool](https://www.nest-simulator.org/)
- **Language:** Python 3.8+
- **HPC:** SLURM job scheduling on compute clusters
- **Libraries:** NumPy, Matplotlib, SciPy
- **Data:** ~500GB per full simulation run

---

## 📈 Key Findings

1. **Noise Resistance:** Network maintained orientation selectivity under 50%+ noise levels
2. **Emergent Dynamics:** Spatiotemporal waves arose from local connectivity without central coordination
3. **Population Coding:** Orientation decoded from ~100 neurons with >80% accuracy
4. **Biological Validity:** Activity patterns matched experimental recordings from macaque V1

---

## 📖 Full Thesis

**Title:** "Stabilization of the Orientation Map in a Computational Model of L4 in V1 of Macaque Monkey"

[📄 Read Full Thesis (PDF)](Masterarbeit_final.pdf)

**Abstract:** Visual cortex layer 4 exhibits orientation selectivity—neurons respond preferentially to edges of specific angles. This thesis investigates the connectivity patterns that stabilize this "orientation map" under noisy, dynamic input, using a large-scale spiking neural network model constrained by experimental data.

---

## 🎓 Context

**Master's Thesis Project**  
Forschungszentrum Jülich (IAS-6 Computational and Systems Neuroscience) & RWTH Aachen University  
Grade: 1.6 (Good) | Oct 2021 – Mar 2024

**Supervisors:** [Add if appropriate]

---

## 🔗 Related Work

Interested in this work? Check out:
- [Time-Series Transformer](https://github.com/SATheinen/attention-stock-predictor) — Temporal prediction with attention mechanisms
- [CNN Segmentation](https://github.com/SATheinen/cloud-type-recognition) — Computer vision for image analysis

---

## 📧 Contact

**Silas Theinen**  
Computational Neuroscientist | Neural Signal Processing

- 📧 silas.theinen@rwth-aachen.de
- 💼 [LinkedIn](https://linkedin.com/in/silas-theinen-058977358)
- 🐙 [GitHub](https://github.com/SATheinen)

---

## 📝 Citation

If you find this work useful, please cite:

```bibtex
@mastersthesis{theinen2024visual,
  title={Stabilization of the Orientation Map in a Computational Model of L4 in V1 of Macaque Monkey},
  author={Theinen, Silas},
  year={2024},
  school={RWTH Aachen University \& Forschungszentrum J\"ulich}
}
```

---

## 🙏 Acknowledgments

This work was conducted at the Institute for Advanced Simulation (IAS-6) at Forschungszentrum Jülich, using their HPC infrastructure. Special thanks to the NEST development team for their excellent simulation toolkit.

---

*Note: Due to the computational scale (1M+ neurons, 1B+ synapses), full simulation code requires HPC resources. Contact me for details on running or adapting this model.*
