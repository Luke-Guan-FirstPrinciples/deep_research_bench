
# Comprehensive Situational Awareness for Cislunar Space Targets: Methods, Constraints, and Near-Term Task Support

**Executive Summary**

What we know: Current cislunar SSA/SDA research is converging on information-driven sensor tasking, optimized constellation design, and autonomous observer trajectory planning to maintain target custody in the Earth–Moon dynamical environment [1–4]. What’s most constrained now is limited/fragmentary measurement geometry and data quality—e.g., adding lunar-based optical observations can reduce orbit-determination errors from “several hundred meters” (ground-only) to “tens of meters” (ground+space+lunar), contingent on lunar-data noise (2025, Precise Orbit Determination… integrated optical observations) [10]. What changes next (≤10 years): progress will hinge on operationally validated multi-sensor networks and closed-loop, real-time tasking/estimation pipelines that can adapt to sparse observations, communication impairments, and non-Keplerian trajectory evolution [1–5,9,11].

## 1. Research Questions & Scope
This report synthesizes methods to (i) conduct comprehensive and accurate situational awareness of space targets in cislunar space and (ii) support the effectiveness of short-term cislunar tracking/monitoring tasks. Covered topics are limited to the provided items: predictive sensor tasking and constellation optimization; autonomous mobile-observer trajectory planning; ground-based EO surveillance demonstrations; initial orbit determination (IOD) from angle-only measurements; long-arc state recovery from sparse/legacy data; communication-performance modeling; and selected perspectives on integrated ground/space/lunar observing architectures and operational challenges [1–5,9–12].

## 2. Methodology
Items were consolidated into five operational categories: (1) sensing/observations, (2) estimation & orbit determination, (3) tasking & scheduling, (4) constellation/network architecture optimization, and (5) operational constraints (communications, dynamics). Only statements explicitly supported by the items are included, and numeric claims are reproduced exactly as given in the items and tied to their source. Web resources and conference portals are treated as background when they are not primary, citable technical papers.

## 3. Key Concepts & Terminology
- SSA/SDA: Space Situational Awareness / Space Domain Awareness (tracking, characterization, custody, and prediction of space objects) [11].
- Cislunar: The Earth–Moon region where three-body dynamics significantly affect trajectories (often modeled with CR3BP concepts) (background) [13,14].
- EIF: Extended Information Filter used for estimation/information-form tasking objectives [1].
- MILP: Mixed-Integer Linear Programming used for discrete constellation/sensor placement and tasking decisions [3].
- p-Median (time-expanded): Facility-location formulation used to place observers/sensors to optimize coverage over time [3].
- Mutual information (MI): Information-theoretic metric used to plan sensing/trajectories to maximize expected knowledge gain [4].
- IOD: Initial Orbit Determination; obtaining an initial state estimate from limited measurements (e.g., angle-only) [8].
- TLE: Two-Line Element set (legacy orbital representation); used as a data source in long-arc recovery methods [9].
- POD: Precise Orbit Determination; high-accuracy state estimation typically using multi-site observations and dynamical modeling [10].

## 4. State‑of‑the‑Art Overview
## At-a-Glance Artifact

| Category (most represented) | Representative regime | Strongest current constraint (number, unit, mass, experiment, year) | Main detection channels | Near-term prospects (≤10 yrs) with named efforts |
|---|---|---|---|---|
| Predictive sensor tasking | Multi-spacecraft / multi-target cislunar tracking | No quantitative constraint provided in items for Tomita et al. tasking performance; uses EIF + linear integer programming (2023, Multi-Spacecraft Predictive Sensor Tasking…) [1] | Space-based optical (implied), tasking/scheduling | Closed-loop tasking + phasing optimization for periodic traffic: Concurrent Optimization of Satellite Phasing and Tasking (2025) [2]; integration into constellation design (2025) [3] |
| Constellation / network design | Patrol constellations; distributed observers | No numeric performance bound given; formulated as time-expanded p-Median MILP with Lagrangian relaxation (2025, Constellation Design… Facility Location Problem) [3] | Distributed space-based sensing (optical implied) | Rapid assessment of near-optimal constellations (2025) [3]; multi-objective system optimization frameworks in AMOS literature (2023) [12] |
| Autonomous mobile observer trajectory planning | Low-thrust/mobile observer in cislunar region | No numeric constraint provided; optimizes via mutual information + sequential convex programming (2024, Information-Based Trajectory Planning…) [4] | Space-based optical tracking/navigation (implied) | Autonomy for tracking/navigation co-optimization with MI metrics (2024) [4]; integration with tasking (aligned with 2023–2025 tasking/constellation work) [1–3] |
| Orbit determination & state recovery | Sparse angles-only IOD; long-arc recovery from legacy/sparse data | “Several hundred meters” (ground-only) vs “tens of meters” (with lunar-based optical added) orbit errors; 2025, Precise Orbit Determination… integrated optical observations [10] | Ground/space/lunar optical observations [10]; angle-only measurements [8]; statistical filtering + TLE reconstruction [9] | Angle-only IOD with 3 measurements for onboard use (2025) [8]; statistically grounded long-arc recovery (2025) [9]; integrated observation architectures emphasized by ESA (2025) [11] |
| Operational sensing demonstrations & comms constraints | Ground-based EO surveillance; cislunar comms under non-Gaussian phenomena | No numeric detection thresholds reported in items; ground-based demonstrations with CMOS-equipped telescopes (2024, LANL ground-based cislunar surveillance) [6] | Ground-based EO; reflectance signature modeling (2024) [6]; comms modeling for tracking data transport (2024) [7] | More operational demonstrations of ground-based surveillance (2024) [6]; comms performance analysis for uncharted/non-Gaussian effects (2024) [7]; strategies for monitoring beyond GEO (ESA, 2025) [11] |

## Complementarity Map (modalities × approaches)
- **Predictive sensor tasking (Tomita 2023)**: Dominant modality now: space-based network scheduling/estimation logic [1]. Overtaken when: operational sensing (ground/space/lunar optical) supplies higher-quality, diverse geometries to feed closed-loop tasking (POD-focused architectures) [10]. Limiting systematic: real-time integration of dynamic measurement availability into tasking (noted gap across items).
- **Phasing + tasking optimization (Patel 2025)**: Dominant modality now: constellation-level optimization for periodic traffic [2]. Overtaken when: on-orbit demonstrations provide empirical observability/custody metrics under real constraints [6,11]. Limiting systematic: scalability to larger heterogeneous fleets (noted gap).
- **Constellation design via facility-location MILP (Shimane 2025)**: Dominant modality now: planning/architecture optimization [3]. Overtaken when: operational frameworks and shared protocols enable multi-stakeholder, multi-sensor networks (ESA operational perspective) [11]. Limiting systematic: robustness under uncertainty/adversarial or degraded conditions (noted gap).
- **Autonomous MI-based trajectory planning (Wolf & Jones 2024)**: Dominant modality now: autonomous space-based observer planning [4]. Overtaken when: comms/latency and measurement uncertainties dictate more conservative autonomy + estimation designs (communications performance considerations) [7]. Limiting systematic: robustness to delays/uncertainty in closed-loop autonomy.
- **Ground-based EO surveillance demonstrations (Sechrest et al. 2024)**: Dominant modality now: ground-based optical detection with signature modeling for magnitude validation [6]. Overtaken when: integrated ground/space/lunar optical networks improve POD and reduce errors to tens of meters (2025 POD study) [10]. Limiting systematic: illumination/geometry constraints and sparse observation opportunities.
- **Angle-only IOD (Jo et al. 2025)**: Dominant modality now: estimation methods for minimal-data regimes [8]. Overtaken when: multi-site (including lunar-based) observations increase information content and reduce orbit errors (POD architectures) [10]. Limiting systematic: sensitivity to measurement noise and limited angles-only geometry.
- **Long-arc recovery (Stivi et al. 2025)**: Dominant modality now: statistical filtering/legacy data recovery [9]. Overtaken when: consistent, higher-rate modern tracking reduces reliance on legacy reconstruction [11]. Limiting systematic: sparse/heterogeneous data consistency over long arcs.

## Limiting Backgrounds & Systematics (and mitigations)
- **Sparse/poor geometry and intermittent visibility (illumination constraints)** → Mitigation: diversify vantage points (ground/space/lunar optical) as emphasized in integrated optical observation architectures [10,11].
- **Measurement noise sensitivity (especially for lunar-based data in integrated POD)** → Mitigation: explicitly model/estimate nuisance parameters such as solar radiation pressure coefficients in POD pipelines [10].
- **Scalability limits in multi-agent optimization (tasking/constellation design)** → Mitigation: use decompositions/relaxations and heuristics (e.g., Lagrangian relaxation in facility-location MILP) to enable rapid near-optimal assessment [3].
- **Comms impairments (non-Gaussian noise, dynamic propagation) affecting timeliness/quality** → Mitigation: incorporate robust communication performance/system analysis into tracking concept of operations [7].
- **Operational validation gap (algorithm-to-ops transition)** → Mitigation: execute ground-based surveillance demonstrations and extend to on-orbit demonstrations for end-to-end custody metrics [6,11].

## 5. Thematic Deep‑Dives
## 1) Observation architecture for cislunar custody (ground/space/lunar)
Integrated optical observing is repeatedly highlighted as a route to higher-accuracy cislunar POD. A 2025 study reports that **ground-based sensors alone achieve “several hundred meters” accuracy**, while **adding lunar-based observations reduces errors to “tens of meters”**, with **lunar-data noise** identified as critical (2025, *Precise Orbit Determination for Cislunar Space Targets Based on Ground/Space/Lunar Based Integrated Optical Observations*) [10].

**Short-term task support implication:** when scheduling limited observation windows, prioritize geometry-diversifying assets (especially non-terrestrial vantage points) to reduce covariance growth between passes, and include estimation of non-gravitational parameters (e.g., solar radiation pressure coefficient) when supported by data [10].

**Forward milestone (named + dated):** mature integrated monitoring strategies as articulated by ESA’s 2025 “Beyond GEO” cislunar monitoring strategy discussions (2025) [11].

## 2) Predictive sensor tasking and concurrent constellation phasing
For multi-observer, multi-target scenarios, Tomita et al. propose a **predictive sensor tasking** approach using an **Extended Information Filter** and solving assignment via **linear integer programming** to mitigate combinatorial growth (2023, *Multi-Spacecraft Predictive Sensor Tasking for Cislunar SSA*) [1]. Patel et al. extend the concept by **concurrently optimizing satellite phasing and tasking** to maximize information coverage for periodic cislunar traffic (2025, *Concurrent Optimization of Satellite Phasing and Tasking…*) [2].

**Quantitative constraint available from items:** improved custody quality is indirectly bounded by achievable POD accuracy when observations are integrated; the best explicit numeric example provided is the “several hundred meters” to “tens of meters” improvement when adding lunar-based optical observations (2025 POD study) [10].

**Forward milestone (named + dated):** deploy/assess phasing+tasking co-optimization frameworks for patrol constellations (2025) [2], and integrate tasking outputs with constellation planning methods (2025) [3].

## 3) Constellation design as a facility-location problem (planning at scale)
Shimane et al. formulate constellation design for cislunar SSA as a **time-expanded p-Median** facility-location problem and apply **MILP**, using **Lagrangian relaxation and heuristics** for rapid near-optimal assessment (2025, *Cislunar SSA Constellation Design and Planning with Facility Location Problem*) [3]. This connects naturally to operational concerns that “a single EO/IR sensor system is insufficient” for persistent cislunar SDA and motivates distributed networks (ESA 2025 perspective) [11].

**Quantitative constraint available from items:** the most explicit numeric custody-performance bound remains the POD accuracy improvement (“several hundred meters” → “tens of meters”) achievable with integrated optical observations (2025) [10], which can serve as a network-level success metric for constellation design validation.

**Forward milestone (named + dated):** operationalize constellation/network optimization approaches discussed in AMOS 2023 works on distributed space-based networks for cislunar SDA (2023, *Optimizing Distributed Space-Based Networks for Cislunar SDA*) [12] alongside 2025 facility-location planning [3].

## 4) Autonomous mobile observers and information-theoretic trajectory planning
Wolf and Jones develop an information-based trajectory planning tool for autonomous absolute tracking in cislunar space, maximizing tracking/navigation performance using **mutual information** and **sequential convex programming** (2024, *Information-Based Trajectory Planning…*) [4]. This addresses the operational need to adapt sensing geometry when targets and observers evolve in a complex dynamical environment.

**Quantitative constraint available from items:** autonomy ultimately inherits measurement-geometry limits reflected in POD accuracy: integrated optical architectures can reach “tens of meters” error (2025 POD study) [10], setting a concrete navigation/tracking performance target for autonomous planners.

**Forward milestone (named + dated):** integrate autonomous planning with robust comms modeling (2024, *Cislunar Communication Performance and System Analysis with Uncharted Phenomena*) to ensure timely delivery of measurements and tasking updates under non-Gaussian channel effects [7].

## 5) Tracking/monitoring pipelines: from detection to IOD to long-arc recovery
- **Ground-based detection & characterization:** LANL demonstrations show ground-based electro-optical surveillance using advanced CMOS-equipped telescopes, with reflectance signature modeling to validate observed magnitudes (2024, *Ground-based Cislunar Space Surveillance Demonstrations…*) [6].
- **Minimal-data IOD for rapid response:** a differential corrections IOD algorithm is proposed using **only three angle-only measurements**, targeting accurate trajectory estimation with minimal data/compute suitable for onboard applications (2025, *Differential Corrections Algorithm for IOD… using Angle-Only Measurements*) [8].
- **Sparse/legacy long-arc state recovery:** a method combining Gaussian-mixture-model filtering and numerical averaging of TLEs aims to recover dynamically coherent states and is validated on historical cislunar missions (2025, *A dynamical coherency gate for state recovery…*) [9].

**Quantitative constraint available from items:** for end-to-end custody accuracy, the clearest numeric benchmark remains the POD accuracy range: “several hundred meters” (ground-only) vs “tens of meters” (with lunar-based optical) reported in 2025 [10].

**Forward milestones (named + dated):**
- Transition ground-based surveillance demonstrations (2024) toward integrated architectures aligned with ESA’s 2025 monitoring strategies [6,11].
- Mature 3-angle IOD for onboard/short-term response contexts (2025) and couple it with robust comms performance assumptions (2024) to ensure timely measurement downlink/uplink [7,8].
- Use long-arc recovery methods (2025) to backfill custody gaps and validate dynamical consistency when observation cadences are low [9].

## 6. Research Gaps & Opportunities
1) **Closed-loop, real-time integration of measurements with predictive tasking.** Success criterion: demonstrate an end-to-end pipeline that ingests integrated optical observations and achieves **“tens of meters”** orbit error (2025, integrated ground/space/lunar POD study) while driving tasking decisions (tasking framework: 2023) [1,10].
2) **Validated heterogeneous-sensor fusion (beyond optical-only emphasis).** Success criterion: publish a benchmarked fusion result that matches or improves the **“tens of meters”** POD error regime (2025, integrated optical POD) using multi-platform data products with quantified noise assumptions [10].
3) **Scalable constellation design for large, heterogeneous fleets.** Success criterion: show rapid near-optimal assessments using the **time-expanded p-Median MILP + Lagrangian relaxation** approach on progressively larger scenario sets (2025) and report custody accuracy against the **“several hundred meters” → “tens of meters”** POD target (2025) [3,10].
4) **Robust autonomous tracking under comms delay/impairments.** Success criterion: integrate MI-based trajectory planning (2024) with a communications performance model addressing **non-Gaussian noise** and dynamic propagation (2024) and report resulting custody error against the 2025 POD benchmark (“tens of meters”) [4,7,10].
5) **Operational demonstrations bridging algorithms to practice (on-orbit or sustained campaigns).** Success criterion: extend ground-based EO demonstration campaigns (2024) to multi-site/multi-asset operations and report achieved orbit errors relative to the 2025 integrated POD ranges [6,10].
6) **Short-term rapid-response IOD from minimal data with quantified performance in cislunar conditions.** Success criterion: demonstrate IOD using **3 angle-only measurements** (2025) feeding a custody pipeline that maintains orbit error within the “several hundred meters” regime for ground-only sensing or better when additional assets are available (2025 POD context) [8,10].
7) **Long-arc custody-gap recovery with clear operational triggers.** Success criterion: define criteria for invoking dynamical coherency gate + GMM/TLE averaging (2025) and show recovery to a state consistent with subsequent integrated POD updates (2025) [9,10].
8) **Access to real-world lunar-based sensor data for validation.** Success criterion: release (or enable controlled-access evaluation of) lunar-based optical datasets with noise characterization sufficient to reproduce the 2025 finding that lunar noise level is critical to reaching “tens of meters” errors [10].

## 7. Implications & Next‑Step Recommendations
1) (0–3y) **Stand up a closed-loop “tasking → observation → estimation → re-tasking” prototype** combining EIF-based predictive tasking (2023) with integrated optical estimation objectives (2025). **Why now:** the limiting systematic is sparse/intermittent geometry; closing the loop directly targets geometry selection to reach the “tens of meters” POD regime [1,10].
2) (0–3y) **Run multi-site ground-based campaigns with standardized photometric/reflectance modeling outputs.** **Why now:** illumination/visibility constraints limit ground-only custody; extending the 2024 ground-based demonstrations into repeatable multi-site products reduces intermittent-observation risk and improves handoff to OD pipelines [6].
3) (0–3y) **Incorporate comms-aware scheduling and buffering into tracking concepts of operations.** **Why now:** non-Gaussian noise and dynamic propagation can degrade timeliness/quality of tracking data; comms-aware designs reduce latency-driven estimation divergence [7].
4) (3–10y) **Scale constellation design using facility-location MILP tooling and validate against custody accuracy targets.** **Why now:** scalability is a stated limiter; the 2025 p-Median/MILP + Lagrangian relaxation approach is designed for rapid assessment and can be anchored to the 2025 POD accuracy ranges as measurable outcomes [3,10].
5) (3–10y) **Integrate autonomous MI-based trajectory planning with network tasking and comms constraints.** **Why now:** autonomy is constrained by uncertainty and delayed updates; coupling 2024 MI-based planning with 2024 comms modeling addresses a key systematic while aiming for the “tens of meters” custody benchmark demonstrated achievable with better geometry [4,7,10].
6) (3–10y) **Develop and publish cislunar SSA benchmarks spanning IOD (3-angle), POD (integrated optical), and long-arc recovery.** **Why now:** lack of standardized evaluation blocks transition to operations; benchmarks can unify rapid-response (2025 IOD), high-accuracy custody (2025 POD), and sparse-arc recovery (2025) into a measurable maturation path [8–10].

## References
1. [Tomita et al., 2023, Multi-Spacecraft Predictive Sensor Tasking for Cislunar Space Situational Awareness](https://arxiv.org/pdf/2310.04894.pdf)
2. [Patel et al., 2025, Concurrent Optimization of Satellite Phasing and Tasking for Cislunar Space Situational Awareness](https://arxiv.org/pdf/2503.16617.pdf)
3. [Shimane et al., 2025, Cislunar Space Situational Awareness Constellation Design and Planning with Facility Location Problem](https://arxiv.org/pdf/2408.06238.pdf)
4. [Wolf and Jones, 2024, Information-Based Trajectory Planning for Autonomous Absolute Tracking in Cislunar Space](https://arxiv.org/pdf/2408.17435.pdf)
5. [Cetin et al., 2024, Cislunar Communication Performance and System Analysis with Uncharted Phenomena](https://arxiv.org/pdf/2409.09426.pdf)
6. [Sechrest et al., 2024, Ground-based Cislunar Space Surveillance Demonstrations at Los Alamos National Laboratory](https://arxiv.org/pdf/2412.03339.pdf)
7. [Jo et al., 2025, Differential Corrections Algorithm for Initial Orbit Determination in the Cislunar Region using Angle-Only Measurements](https://arxiv.org/pdf/2507.22350.pdf)
8. [Stivi et al., 2025, A dynamical coherency gate for state recovery: Statistical requiem for the long arc of cislunar orbital mis-prediction](https://arxiv.org/pdf/2506.22748.pdf)
9. [Zhang et al., 2025, Precise Orbit Determination for Cislunar Space Targets Based on Ground/Space/Lunar Based Integrated Optical Observations](https://ui.adsabs.harvard.edu/abs/2025SoSyR..59...80Z/abstract)
10. [ESA Space Debris Office, 2025, Beyond GEO: Strategies for monitoring cislunar environment](https://conference.sdo.esoc.esa.int/proceedings/sdc9/paper/258)
11. [Barker et al., 2023, Optimizing Distributed Space-Based Networks for Cislunar Space Domain Awareness](https://ui.adsabs.harvard.edu/abs/2023amos.conf...70B/abstract)
12. [Three-Body Periodic Orbits - JPL Solar System Dynamics](https://ssd.jpl.nasa.gov/tools/periodic_orbits.html) (background)
13. [SOLAR SAIL ORBITS IN CISLUNAR SPACE FOR LUNAR ...](https://ntrs.nasa.gov/api/citations/20250006966/downloads/Solar%20Sail%20Orbits%20in%20Cislunar%20Space.pdf?attachment=true) (background)
14. [2023 Technical Papers - AMOS Conference](https://amostech.com/2023-technical-papers/) (background)
15. [2021 Technical Papers - AMOS Conference](https://amostech.com/2021-technical-papers/) (background)
16. [Space-based debris trajectory estimation using vision sensors and ...](https://www.sciencedirect.com/science/article/pii/S0094576525000396) (background)
17. [DRAFT / PRE-DECISIONAL - Space Force](https://www.starcom.spaceforce.mil/Portals/2/SDP%203-100%20Space%20Domain%20Awareness%20(November%202023)_pdf_safe.pdf) (background)
