
# Recent demonstrations (>200 qubits) of neutral-atom quantum processors using optical-tweezer arrays

**Executive Summary**

We know that optical-tweezer neutral-atom platforms have now demonstrated both very large physical-qubit arrays and, separately, logical-level control elements needed for fault-tolerant operation, including mid-circuit measurement and error-correction primitives in reconfigurable arrays [1][2]. What’s most constrained now is scaling *high-fidelity two-qubit entangling operations* and QEC cycles to the full scale of the largest arrays; for example, a 2025 “A tweezer array with 6,100 highly coherent atomic qubits” experiment reported 6,100 qubits with 12.6 s coherence time but does not (in these items) report two-qubit gate benchmarks at that same scale [1]. Over the next ≤10 years, progress is likely to be driven by architectures that combine (i) large, zone-based tweezer registers with (ii) mid-circuit reuse/erasure handling and (iii) modular interconnects between processors [2][3][4].

## 1. Research Questions & Scope
This report covers experimental demonstrations and enabling techniques for neutral-atom quantum processors in optical-tweezer arrays with >200 qubits, emphasizing: (i) large-array trapping/coherence/imaging performance, (ii) demonstrated logical-/fault-tolerant architectural mechanisms on reconfigurable atom arrays, (iii) gate/control approaches relevant to scaling, and (iv) near-term architectural directions including mid-circuit erasure conversion and modular interconnects. 

Included: Cs-133 large arrays; Rb-87/Rydberg-array processor demonstrations (as provided); Yb-171 metastable-qubit erasure conversion and atom replacement; compilation/scheduling for dynamically reconfigurable arrays; and modular interconnect proposals.

Excluded: claims without quantitative metrics in the provided items; any results not explicitly contained in the supplied sources.

## 2. Methodology
Only statements supported by the provided items are included, with inline citations mapped to the reference list. Experimental results are presented as quantitative metrics tied to a named experiment and year when such details were present in items. When a cited work is older than ~18 months relative to the current date (2026-03), it is marked as (background) in References. Web/blog/news-style sources are not used as primary references unless marked (background).

## 3. Key Concepts & Terminology
- **Optical tweezer array**: A configurable set of tightly focused laser traps that hold individual neutral atoms as qubits.
- **Neutral-atom qubit**: Qubit encoded in internal atomic states (e.g., hyperfine or metastable/nuclear-spin states) of a neutral atom.
- **Rydberg gate / Rydberg blockade**: Two-qubit entangling mechanism using strong interactions between atoms excited to Rydberg states.
- **Mid-circuit measurement**: Measuring some qubits during a circuit and using results for subsequent operations.
- **Erasure conversion**: Mapping certain error processes into *detectable* loss/erasure events that can be handled by QEC.
- **Zone-based (zoned) architecture**: Separating regions for storage, gates, measurement, and transport to reduce crosstalk and manage entropy.
- **Logical qubit / QEC**: Encoding information redundantly across many physical qubits to detect/correct errors.
- **LDPC code**: Quantum low-density parity-check code; potentially advantageous under erasure-biased noise.
- **Lattice surgery / transversal gates**: Fault-tolerant operations used in surface-code-like schemes.

## 4. State‑of‑the‑Art Overview
## At-a-Glance Artifact

| Category (from items) | Representative mass range | Strongest current constraint (number, unit, mass, experiment, year) [N] | Main detection channels | Near-term prospects (≤10 yrs) with named experiments |
|---|---:|---|---|---|
| Large-scale tweezer-array coherence & imaging | **6,100 qubits** | **12.6 s** coherence time, **“A tweezer array with 6,100 highly coherent atomic qubits” (2025)** [1] | Coherence-time measurement; imaging fidelity/survival characterization | Extend from high-coherence registers to large-scale operations using zone-based transport suggested by the same platform [1] |
| Logical-level control on reconfigurable atom arrays | **Hundreds of qubits** | Logical-processor capability is demonstrated (mid-circuit measurement/control and logical operations) in **“Logical quantum processor based on reconfigurable atom arrays” (2023)** [2] | Mid-circuit readout; logical circuit performance benchmarks | Build toward broader fault-tolerant mechanisms demonstrated in **“Architectural mechanisms of a universal fault-tolerant quantum computer” (2025)** [5] |
| Fault-tolerant architecture mechanisms (universal FT elements) | **Hundreds of qubits** | Universal FT architectural mechanisms (repeated QEC, transversal gates, lattice surgery, mid-circuit reuse) in **“Architectural mechanisms of a universal fault-tolerant quantum computer” (2025)** [5] | Repeated QEC cycles; mid-circuit reuse; syndrome extraction/processing | Scale these mechanisms to larger physical-qubit counts, using large-coherence arrays as hardware substrate [1][5] |
| Erasure conversion & atom replacement (Yb metastable qubits) | **Array-scale (not quantified here)** | Mid-circuit erasure conversion and high-fidelity gates in **“High-fidelity gates with mid-circuit erasure conversion in a metastable neutral atom qubit” (2023)** [6] | Detectable loss/erasure events + QEC handling | “Fast, continuous and coherent atom replacement in a neutral atom qubit array” (2025) targets continuous reloading during computation [7] |
| High-fidelity parallel entangling gates (Rydberg) | **Up to 60 atoms** | **99.5%** parallel entangling gates on **up to 60 atoms**, **“High-fidelity parallel entangling gates on a neutral atom quantum computer” (2023)** [8] | Two-qubit gate fidelity characterization; parallel operation benchmarks | Integrate high-fidelity parallel gates with mid-circuit QEC and reconfigurable connectivity demonstrated in logical-processor/FT-architecture works [2][5][8] |

## Complementarity Map (modality matrix)

- **Large coherent Cs tweezer registers (6,100-qubit class)**: 
  - Dominates now: **astro/engineering performance** (coherence, imaging, transport at scale) [1].
  - Overtaken by: **processor-level logical/QEC demonstrations** when evaluating fault-tolerant primitives (currently shown on smaller arrays) [2][5].
  - Limiting systematic: scaling from register metrics to **large-scale entangling-gate + QEC-cycle** performance (not quantified at 6,100-qubit scale in items) [1].

- **Reconfigurable atom-array logical processors (hundreds of qubits)**:
  - Dominates now: **processor demonstrations** of logical operations/mid-circuit capabilities [2].
  - Overtaken by: **larger physical-qubit registers** for total capacity/overhead (e.g., 6,100-qubit arrays) [1].
  - Limiting systematic: **overhead/circuit depth** associated with connectivity, scheduling, and error-management (addressed by compilation and zoned state-prep work) [9][10].

- **Fault-tolerant architectural mechanisms (universal FT elements)**:
  - Dominates now: **QEC/FT protocol demonstrations** (repeated QEC, lattice surgery, mid-circuit reuse) [5].
  - Overtaken by: **continuous-reload/erasure-handling hardware** if atom loss becomes the dominant barrier to deeper circuits (hardware path) [6][7].
  - Limiting systematic: **entropy management / qubit reuse under mid-circuit operations** (explicitly highlighted as a design principle) [5].

- **Yb metastable qubits with erasure conversion and atom replacement**:
  - Dominates now: **hardware error-model shaping** via erasure conversion and atom replacement [6][7].
  - Overtaken by: **code choices** (e.g., LDPC under erasure-biased noise) as logical performance targets tighten [11].
  - Limiting systematic: reliable **mid-circuit operation with loss detection + replacement** without disturbing computation [6][7].

- **Rydberg parallel gate control (up to 60 atoms at 99.5%)**:
  - Dominates now: **gate-level fidelity and parallelism** [8].
  - Overtaken by: **full-stack FT/QEC cycles** as soon as gates are embedded into repeated QEC with feedforward [5].
  - Limiting systematic: scaling **motion/dephasing/leakage and crosstalk** as arrays become denser and more parallel (noted as a key gap in control items) [8][12].

## Limiting Backgrounds & Systematics (with mitigation)

- **Atom loss limiting circuit depth** → Mitigation: **continuous coherent atom replacement** during computation (2025 “Fast, continuous and coherent atom replacement…”) [7].
- **Gate dephasing/leakage at scale** → Mitigation: **optimal-control and dark-state based parallel gate protocols** (2023 “High-fidelity parallel entangling gates…”) [8].
- **Idling/crosstalk in large zoned architectures** → Mitigation: **hardware-aware minimal instruction schedules** that shield idling qubits (2025 “Optimal State Preparation for Logical Arrays on Zoned Neutral Atom Quantum Computers”) [10].
- **Correlated phase errors impacting QEC** → Mitigation: **mid-circuit correction using spectator qubits and feed-forward** (2023 “Mid-circuit correction of correlated phase errors…”) [13].
- **Inter-module entanglement rate/fidelity bottlenecks for modular scaling** → Mitigation: cavity/photon-collection-based **high-rate, high-fidelity modular interconnects** (2024 “High-rate and high-fidelity modular interconnects…”) [3].

## 5. Thematic Deep‑Dives
## 1) >200-qubit demonstrations in optical tweezer arrays: what is actually demonstrated

### 1.1 Large-scale physical-qubit arrays (coherence/imaging/transport)
- Quantitative demonstration: **6,100 qubits** with **12.6 s** coherence time in **2025 “A tweezer array with 6,100 highly coherent atomic qubits”** [1].
- Additional quantitative metrics reported for the same 2025 experiment: **23 min** trapping lifetime; **>99.99%** imaging fidelity; **99.98952%** imaging survival probability; **99.9834%** single-qubit gate fidelity; **610 µm** transport with **99.95%** transport fidelity [1].
- Milestone (forward-looking, grounded in items): use these register-level metrics to support **zone-based architectures and QEC with thousands of physical qubits** (explicitly framed as the pathway in the 2025 work) [1].

### 1.2 Logical-/fault-tolerant architecture elements on hundreds of atoms
- Quantitative constraint (array scale): The items describe processors with **up to 256 Yb atoms** for fault-tolerant protocols in **2025 “Fault-tolerant quantum computation with a neutral atom processor”** [14].
- Demonstrated architectural elements: **repeated QEC, transversal gates, lattice surgery, and mid-circuit qubit reuse** in **2025 “Architectural mechanisms of a universal fault-tolerant quantum computer”** [5].
- Milestone: scaling these demonstrated FT mechanisms from hundreds of atoms toward the **thousands-qubit** regime enabled by large coherent tweezer arrays [1][5].

## 2) Error models and QEC-enabling hardware: erasure conversion and atom replacement

### 2.1 Mid-circuit erasure conversion as an architectural lever
- Quantitative constraint: Yb metastable neutral-atom qubits achieved **0.999** single-qubit and **0.98** two-qubit gate fidelities in **2023 “High-fidelity gates and mid-circuit erasure conversion in an atomic qubit”** [15] (background) and are further developed in the arXiv version emphasizing mid-circuit erasure conversion [6].
- Rationale from items: converting error sources into **detectable erasures** improves the tractability of QEC and logical performance [6][14].
- Milestone: combine mid-circuit erasure conversion with larger-scale fault-tolerant protocols demonstrated on **up to 256 atoms (2025)** [14].

### 2.2 Continuous atom replacement to overcome loss-limited depth
- Quantitative anchor (date + experiment present): the approach is presented as **2025 “Fast, continuous and coherent atom replacement in a neutral atom qubit array”** [7]. (The provided items do not include a numerical rate/latency; no additional numbers are asserted.)
- Milestone: demonstrate **scalable, real-time atom replacement in larger and more complex arrays** as an explicit next-step gap identified in items, enabling deeper circuits without being loss-limited [7].

## 3) Gate and control performance relevant to scaling beyond 200 qubits

### 3.1 Parallel Rydberg entangling gates
- Quantitative constraint: **99.5%** parallel entangling gates on **up to 60 atoms** in **2023 “High-fidelity parallel entangling gates on a neutral atom quantum computer”** [8].
- Milestone: integrate this class of parallel entangling operations with mid-circuit QEC and reuse primitives shown in **2025 “Architectural mechanisms…”** [5] to approach end-to-end logical-cycle demonstrations with higher parallelism.

### 3.2 Correlated-error correction with mid-circuit techniques
- Quantitative anchor (date + experiment present): **2023 “Mid-circuit correction of correlated phase errors using an array of spectator qubits”** demonstrates mid-circuit correction with real-time feed-forward [13]. (No quantitative suppression factor is included in the provided summary; none is asserted.)
- Milestone: combine spectator-qubit correction methods with repeated QEC and mid-circuit reuse from **2025 “Architectural mechanisms…”** [5].

## 4) Compiler/scheduler and architecture co-design for dynamically reconfigurable arrays

### 4.1 Compiling for dynamically field-programmable qubit arrays (DPQA)
- Quantitative constraint: not provided in the items for overhead reduction; thus excluded.
- Qualitative (non-quantitative) statement limited to items: DPQA compilation is used to reduce two-qubit gate overhead and circuit depth versus fixed connectivity, via in-situ reconfiguration [9].
- Milestone: connect DPQA compilation [9] to zoned logical state-preparation schedules in **2025 “Optimal State Preparation for Logical Arrays on Zoned Neutral Atom Quantum Computers”** [10] to support larger logical arrays with reduced idling/crosstalk.

## 5) Modular scaling direction (interconnects)

### 5.1 High-rate, high-fidelity modular interconnects (proposal direction)
- Quantitative constraint: no rates/fidelities are numerically specified in the provided item text, so none are asserted.
- Grounded direction: **2024 “High-rate and high-fidelity modular interconnects between neutral atom quantum processors”** proposes optical-cavity-based remote entanglement and improved photon collection [3].
- Milestone: demonstrate these interconnects experimentally in multi-module settings as identified as a gap in items [3].

## 6. Research Gaps & Opportunities
1) **Demonstrate large-scale entangling-gate benchmarks on >200-qubit (ideally >1,000-qubit) tweezer arrays.** Success criterion: report two-qubit gate fidelity and/or Bell-state fidelity benchmarks on an array **>200 qubits** in a named experiment/year (not yet present for the 6,100-qubit platform in items) [1].

2) **Scale repeated QEC cycles and mid-circuit reuse to larger physical-qubit counts.** Success criterion: perform repeated QEC with mid-circuit measurement/reuse on **>256 atoms** in a named experiment/year (current scale cited: **256 atoms** in 2025 FT demonstration) [14].

3) **Integrate erasure conversion with full-stack FT protocols.** Success criterion: demonstrate a logical/QEC cycle that explicitly uses mid-circuit erasure conversion (from 2023 Yb work) inside a fault-tolerant computation protocol in a named experiment/year [6][15].

4) **Demonstrate scalable, coherent atom replacement without computation disturbance in larger arrays.** Success criterion: publish a measured replacement/reload performance metric (rate or latency) in the context of **2025 “Fast, continuous and coherent atom replacement…”**-style operation, at an array size >200 qubits [7].

5) **Quantify and mitigate correlated errors under mid-circuit operations.** Success criterion: report a quantitative correlated-phase-error suppression metric in a mid-circuit spectator-qubit protocol and show compatibility with QEC cycles in a named experiment/year [13][5].

6) **Hardware-aware scheduling for zoned logical arrays with measurable fidelity gain.** Success criterion: provide experimental or end-to-end simulated improvement metric (e.g., logical state-prep fidelity or reduced idle error) using the 2025 SMT-solver scheduling approach in a named processor setting [10].

7) **Experimentally validate modular interconnect performance.** Success criterion: report remote entanglement **rate (Hz or s⁻¹)** and **fidelity (%)** between two neutral-atom modules in a named experiment/year aligned with the 2024 modular-interconnect proposal direction [3].

8) **Match LDPC-code proposals to measured erasure-biased noise.** Success criterion: extract an experimental erasure-biased noise model from a processor using erasure conversion and demonstrate a logical-error suppression benchmark using an LDPC code design tailored to that bias (LDPC proposal: 2025) [11][6].

## 7. Implications & Next‑Step Recommendations
1) (0–3y) **Publish standardized two-qubit/parallel-gate benchmarks on >200-qubit arrays and report scaling curves.** Why now: the dominant constraint is translating large-array coherence/imaging [1] into large-array entangling performance; this targets the gate dephasing/leakage scaling systematic highlighted in control-focused items [8].

2) (0–3y) **Integrate mid-circuit erasure conversion into repeated-QEC demonstrations.** Why now: erasure conversion directly mitigates atom-loss/error-model limitations [6][14] and addresses the atom-loss-limited circuit-depth systematic [7].

3) (0–3y) **Adopt hardware-aware zoned scheduling/state preparation for logical arrays and quantify its impact.** Why now: idling/crosstalk in zoned architectures is a limiting systematic; the 2025 SMT-solver method is explicitly aimed at shielding idling qubits [10].

4) (3–6y) **Scale fault-tolerant architectural mechanisms (lattice surgery, transversal gates, mid-circuit reuse) to larger physical-qubit registers.** Why now: the 2025 FT architectural mechanisms demonstration provides the protocol blueprint, but scaling is limited by entropy management and mid-circuit reuse overheads [5].

5) (3–6y) **Demonstrate continuous atom replacement in the presence of ongoing mid-circuit measurement and feed-forward.** Why now: atom loss is identified as a core depth limiter; continuous replacement is the direct mitigation but must be shown compatible with mid-circuit operations [7][13].

6) (3–10y) **Execute a two-module neutral-atom interconnect experiment reporting rate and fidelity, then connect modules to run a distributed QEC primitive.** Why now: modular scaling is limited by interconnect rate/fidelity; the 2024 interconnect proposal identifies the path via cavities/photon collection but needs experimental validation [3].

7) (3–10y) **Co-design QEC codes with measured erasure-biased noise (including LDPC exploration).** Why now: once erasure conversion is operational, code choice becomes the leverage point; 2025 LDPC-for-erasure-biased work provides a direction but requires coupling to measured noise [11][6].

## References
1. [Ebadi et al., 2025, A tweezer array with 6,100 highly coherent atomic qubits](https://www.nature.com/articles/s41586-025-09641-4)
2. [Bluvstein et al., 2023, Logical quantum processor based on reconfigurable atom arrays](https://arxiv.org/pdf/2312.03982.pdf)
3. [Li and Thompson, 2024, High-rate and high-fidelity modular interconnects between neutral atom quantum processors](https://arxiv.org/pdf/2401.04075.pdf)
4. [Young et al., 2024, An architecture for quantum networking of neutral atom processors](https://arxiv.org/pdf/2202.01634.pdf) (background)
5. [Bluvstein et al., 2025, Architectural mechanisms of a universal fault-tolerant quantum computer](https://arxiv.org/pdf/2506.20661.pdf)
6. [Ma et al., 2023, High-fidelity gates with mid-circuit erasure conversion in a metastable neutral atom qubit](https://arxiv.org/pdf/2305.05493.pdf) (background)
7. [Li et al., 2025, Fast, continuous and coherent atom replacement in a neutral atom qubit array](https://arxiv.org/pdf/2506.15633.pdf)
8. [Evered et al., 2023, High-fidelity parallel entangling gates on a neutral atom quantum computer](https://arxiv.org/pdf/2304.05420.pdf) (background)
9. [Tan et al., 2024, Compiling Quantum Circuits for Dynamically Field-Programmable Neutral Atoms Array Processors](https://arxiv.org/pdf/2306.03487.pdf)
10. [Stade et al., 2025, Optimal State Preparation for Logical Arrays on Zoned Neutral Atom Quantum Computers](https://arxiv.org/pdf/2411.09738.pdf)
11. [Pecorari and Pupillo, 2025, Quantum LDPC codes for erasure-biased atomic quantum processors](https://arxiv.org/pdf/2502.20189.pdf)
12. [Su et al., 2024, Rabi-error and Blockade-error-resilient All-Geometric Rydberg Quantum Gates](https://arxiv.org/pdf/2302.03276.pdf) (background)
13. [Singh et al., 2023, Mid-circuit correction of correlated phase errors using an array of spectator qubits](https://arxiv.org/pdf/2208.11716.pdf) (background)
14. [Reichardt et al., 2025, Fault-tolerant quantum computation with a neutral atom processor](https://arxiv.org/pdf/2411.11822.pdf)
15. [Ebadi et al., 2023, High-fidelity gates and mid-circuit erasure conversion in an atomic qubit](https://www.nature.com/articles/s41586-023-06438-1) (background)
