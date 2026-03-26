
# Exploring Horizontal Gene Transfer (HGT) in Plants and Animals (Non‑Microbial Systems): Evidence, Constraints, and Evolutionary Significance

**Executive Summary**

We know that horizontal gene transfer (HGT) can and does occur in eukaryotes, with especially clear, repeated examples in plants (including mitochondria and parasitic plant–host exchanges) and documented cases in animals where transferred genes confer novel metabolic capabilities [1][2]. What is most constrained now is confident, standardized detection in complex eukaryotic genomes—e.g., one benchmarked land‑plant case reports 57 gene families of prokaryotic/fungal/viral origin in Physcomitrella patens (2012) [1], but comparable, contamination‑robust estimates across animal clades remain sparse [3][4]. Over the next ≤10 years, improved pipelines and functional annotation (including standardized HGT workflows and gene-function prediction methods) should shift the field from anecdotal case studies to cross‑taxon, quantitatively comparable catalogs of candidate transfers [5][6].

## 1. Research Questions & Scope
This report synthesizes evidence and open questions on horizontal gene transfer (HGT) in multicellular eukaryotes—focused on plants and animals. It covers: (i) well-supported instances and representative case studies; (ii) mechanistic routes that plausibly mediate transfer and/or retention; (iii) evolutionary significance where supported by the provided sources; and (iv) current detection/validation limitations and near-term methodological opportunities. Microbial HGT is discussed only as it informs mechanisms relevant to plant/animal systems (e.g., DNA uptake routes, mobile elements) and not as a comprehensive review of bacterial population genetics.

## 2. Methodology
Only the provided, Critic-validated items were used. Claims are restricted to statements supported in those items, with numbered inline citations aligned to the reference list. Priority was given to more recent primary literature where available; older or review-style sources are explicitly marked as (background) in References. Quantitative statements were included only when a number and context were present in the items; where the items did not provide quantitative rates/constraints, the report avoids extrapolation and instead frames actionable gaps and success criteria around benchmarking and validation outcomes rather than estimated frequencies.

## 3. Key Concepts & Terminology
- **HGT (Horizontal Gene Transfer):** Movement of genetic material across species boundaries outside parent-to-offspring inheritance.
- **LGT (Lateral Gene Transfer):** Often used synonymously with HGT.
- **T-DNA:** DNA segment transferred from Agrobacterium to plants during natural transformation.
- **T4SS (Type IV Secretion System):** A secretion apparatus used by some bacteria to transfer DNA/proteins to other cells.
- **Phylogenetic incongruence:** A signature of potential HGT where a gene tree conflicts with the accepted species tree.
- **Transposon:** A mobile genetic element that can move within genomes and, in some cases, between species.
- **Contamination (in genomics):** Exogenous DNA (e.g., microbial) introduced during sampling/sequencing/assembly that can mimic HGT if not controlled.
- **Functional retention:** Persistence of a transferred gene because it is expressed and contributes to fitness/phenotype in the recipient lineage.

## 4. State‑of‑the‑Art Overview
## 3.1 At-a-Glance Artifact (5 key categories represented in the items)

| Category | Representative mass range | Strongest current constraint (number, unit, mass, experiment, year) [N] | Main detection channels | Near-term prospects (≤10 yrs) with named experiments |
|---|---:|---|---|---|
| Land-plant nuclear HGT associated with terrestrial adaptation | Gene families (dozens-scale) | **57 gene families**, Physcomitrella patens, **Widespread impact of HGT on plant colonization of land (2012)** [1] | Comparative genomics; phylogenetic incongruence; functional inference from gene families | Expansion to broader plant phylogenies using standardized HGT pipelines (e.g., **hgtseq (2022)**) and improved gene-function prediction workflows (LLM+KG approaches, **2024**) [5][6] |
| Plant–plant/plant–host HGT in parasitic systems | Genes (100+ scale) | **>100 functional genes**, parasitic plants (dodder), **reported 2019** [7] | Comparative genomics across host/parasite; expression evidence (where available) | Systematic cross-species regulatory motif mapping (e.g., **GOLEM (2023)**) paired with standardized HGT screening to reduce false positives [8][5] |
| Plant mitochondrial HGT and organellar “mosaic” genomes | Foreign mitochondrial genes (dozens–hundreds) | “**dozens to hundreds**” foreign mitochondrial genes in Amborella (reported in plant HGT overview, **2007**) (background) [9] | Organelle genome assembly/comparison; phylogenetic incongruence | Better organelle assemblies and contamination-aware workflows integrated into standardized pipelines (e.g., **hgtseq (2022)**) [5] |
| Animal HGT via mobile elements (host–parasite mediated transposon transfer) | Transposon families | Host–parasite horizontal transfer of transposons documented (example study **2010**) (background) [10] | Comparative genomics of mobile elements; phylogenetic/sequence identity patterns | Broader sampling of vectors/hosts + standardized criteria to discriminate shared ancestry vs transfer; integration with contamination controls emphasized in HGT detection work (e.g., **hgtseq (2022)**) [5][10] |
| Animal metabolic novelty via HGT (fungal carotenoid genes) | Specific metabolic genes/pathways | Horizontally transferred fungal carotenoid genes in Tetranychus urticae (PNAS, **2011**) (background) [2] | Gene phylogenies; pathway presence/absence; expression/functional inference | Extending case-study paradigm to systematic scans in diverse arthropods and other taxa using standardized detection and improved annotation (LLM+KG, **2024**) [6][2] |

## 3.2 Complementarity Map (modalities & limiting systematics)

- **Plant nuclear HGT (e.g., Physcomitrella case):**
  - Dominant modality now: **comparative genomics/phylogenetics** [1].
  - Where another modality overtakes: **functional annotation/interpretation** becomes decisive once large candidate sets exist (gene-function prediction bottleneck) [6].
  - Limiting systematic: **annotation incompleteness and misannotation in non-model eukaryotes** [11][6].

- **Parasitic plant–host transfers (dodder):**
  - Dominant modality now: **comparative genomics across intimate ecological interactions** [7].
  - Where another modality overtakes: **regulatory/sequence-context analyses** (promoter/motif distribution) to evaluate integration/retention plausibility [8].
  - Limiting systematic: **distinguishing genuine HGT from assembly artifacts/contamination in complex plant datasets** [5][4].

- **Plant mitochondrial HGT (Amborella-like mosaicism):**
  - Dominant modality now: **organelle comparative genomics** (background) [9].
  - Where another modality overtakes: **pipeline-level contamination and read/contig provenance analysis** to validate foreign segments [5].
  - Limiting systematic: **confounding by organelle-nuclear transfers, gene loss, and complex evolutionary histories** [4].

- **Animal transposon HGT (host–parasite):**
  - Dominant modality now: **mobile-element comparative genomics** (background) [10].
  - Where another modality overtakes: **population-level sampling and phylogenetic resolution** to time transfers vs shared ancestry (not quantified in items; noted as need). 
  - Limiting systematic: **ancient paralogy/shared ancestral transposons vs true horizontal transfer** [4].

- **Animal metabolic gene HGT (carotenoids in arthropods):**
  - Dominant modality now: **gene phylogenies + pathway novelty** (background) [2].
  - Where another modality overtakes: **functional characterization** to link transferred genes to phenotype/fitness (items describe novelty but do not quantify fitness effects) [2].
  - Limiting systematic: **functional inference without standardized validation criteria across taxa** [4][6].

## 3.3 Limiting Backgrounds & Systematics (and mitigation)

- **Contamination and mis-binning in eukaryotic genome projects can mimic HGT** [5][4].  
  *Mitigation:* apply standardized workflows with explicit contamination assessment (e.g., **hgtseq (2022)**) plus provenance checks from raw reads to assemblies [5].

- **Gene loss, ancient paralogy, and complex histories can look like HGT in phylogenies** [4].  
  *Mitigation:* require multi-pronged evidence (phylogenetic incongruence + composition/context checks + synteny/assembly validation where feasible) as recommended in HGT detection discussions [4].

- **Annotation bottlenecks in non-model eukaryotes limit functional interpretation and can inflate false positives** [11][6].  
  *Mitigation:* use improved annotation tooling and gene-function prediction approaches, including LLM+knowledge-graph strategies (2024) and modern genome annotation tools for non-model eukaryotes (2021) [6][11].

- **Limited benchmarks make sensitivity/specificity of automated HGT calls hard to compare across studies** [4][5].  
  *Mitigation:* create shared benchmark datasets and evaluation criteria; use standardized pipelines (hgtseq, 2022) to improve comparability [5].

- **Regulatory integration is under-characterized, complicating assessments of retention and phenotypic impact** [12][13].  
  *Mitigation:* integrate motif-localization and promoter-element distribution tools (e.g., **GOLEM (2023)**) and cross-species expression modeling (e.g., **DeepPlantCRE (2025)**) into HGT candidate evaluation [8][14].

## 5. Thematic Deep‑Dives
## 4.1 How common is HGT in plants vs animals? What we can quantify from current evidence

- **Plants (quantified exemplar):** A land-plant genomic analysis identified **57 gene families** of prokaryotic, fungal, or viral origin in **Physcomitrella patens** in the study **“Widespread impact of horizontal gene transfer on plant colonization of land” (2012)** [1]. This provides a concrete, genome-wide “order-of-magnitude” anchor for at least one well-studied lineage.
- **Plants (parasitic systems, quantified exemplar):** Parasitic plants (dodder) are reported to have acquired **>100 functional genes** from hosts in a **2019** report [7].
- **Animals (case-study evidence in items, not frequency-quantified):** Documented examples include horizontally transferred fungal carotenoid genes enabling carotenoid biosynthesis in the two-spotted spider mite (**2011**) [2] and host–parasite mediated horizontal transfer of transposons (**2010**) [10]. The items do not provide a comparable “genes per genome” frequency estimate for animals.

**Forward-looking milestone (methods, dated):** Adoption of standardized, contamination-aware pipelines such as **hgtseq (2022)** and improved gene-function prediction approaches using **LLM + knowledge graphs (2024)** as routine components of eukaryotic genome projects should enable cross-study comparability of HGT candidate catalogs within the next decade [5][6].

## 4.2 Mechanisms in plants: from Agrobacterium-like DNA delivery to ecological intimacy

- **Mechanistic anchor (plants):** The best-characterized natural route is **Agrobacterium-mediated transformation** (T-DNA transfer to plant genomes via a secretion system), described as a stable integration pathway in the provided plant-mechanisms summary [15].
- **Ecology-linked transfers (quantified exemplar):** In parasitic plant systems, dodder’s **>100 functional genes** acquired from hosts (2019) implies that sustained physical connectivity and molecular exchange can correlate with higher apparent transfer counts [7].

**Limiting systematic:** Outside Agrobacterium, the items emphasize that mechanisms for non-Agrobacterium pathways are still unclear and that robust discrimination from artifacts is required [15][5].

**Forward-looking milestone (dated):** Use promoter/regulatory-element mapping (e.g., **GOLEM (2023)**) and cross-species expression modeling (e.g., **DeepPlantCRE (2025)**) to test whether candidate HGT genes show atypical promoter motif distributions or regulatory integration patterns compared with native genes [8][14].

## 4.3 Mechanisms in animals: mobile elements, host–parasite interfaces, and metabolic novelty

- **Mobile-element transfers (background exemplar):** Host–parasite interactions can mediate horizontal transfer of **transposons** across animal phyla (Nature, **2010**) [10]. While the items do not quantify rates, the mechanism highlights how intimate biological interactions may bypass typical germline barriers.
- **Metabolic novelty (background exemplar):** In arthropods, horizontally transferred **fungal carotenoid genes** were reported in the two-spotted spider mite (**2011**), demonstrating that HGT can introduce entirely new biosynthetic capabilities into an animal lineage [2].

**Limiting systematic:** The central detection problem is distinguishing true HGT from confounders such as ancient paralogy, gene loss, and contamination—issues emphasized in HGT detection discussions [4][5].

**Forward-looking milestone (dated):** Apply standardized HGT pipelines with contamination assessment (e.g., **hgtseq (2022)**) to broader animal genome datasets specifically targeting mobile elements and metabolic pathway genes, paired with improved functional annotation via **LLM+KG methods (2024)** to interpret candidate transfers [5][6].

## 4.4 Detection and validation in complex eukaryotic genomes: why “rare” is hard to measure

- **Core detection principle:** Phylogenetic incongruence remains a cornerstone approach, but eukaryotic genome complexity makes false positives more likely [4].
- **Pipeline standardization (dated):** **hgtseq (2022)** is described as a standardized pipeline that processes unmapped reads, classifies them taxonomically, flags potential HGT candidates, and includes contamination assessment—explicitly addressing a key failure mode for eukaryotic HGT claims [5].
- **Quantified exemplar motivating the need for standardization:** The plant benchmark of **57 gene families** in **Physcomitrella patens (2012)** [1] shows that large candidate sets can arise—making validation and comparability decisive.

**Forward-looking milestone (dated):** Address the annotation bottleneck using non-model genome annotation tooling (2021) and gene-function prediction strategies (LLM+KG, 2024), enabling higher-confidence functional interpretation of HGT candidates rather than relying solely on sequence similarity [11][6].

## 6. Research Gaps & Opportunities
1) **Cross-taxon benchmarking of eukaryotic HGT detection.**
   - Success criterion: Publish a benchmark suite where a standardized pipeline (e.g., **hgtseq, 2022**) achieves reproducible candidate lists across multiple plant and animal genomes under explicit contamination controls [5].

2) **Standard criteria to separate HGT from gene loss/ancient paralogy in eukaryotes.**
   - Success criterion: For benchmark genomes, demonstrate that candidate calls remain stable under alternative species-tree assumptions and paralog filtering, reducing ambiguous calls flagged in HGT detection discussions [4].

3) **Functional validation framework for “adaptive HGT” in multicellular eukaryotes.**
   - Success criterion: For at least one established case class (e.g., carotenoid pathway genes in arthropods, 2011), define and apply a standardized functional-evidence checklist (expression + pathway consistency), enabling consistent comparisons across taxa [2].

4) **Integration of regulatory evidence into HGT candidate evaluation in plants.**
   - Success criterion: For plant HGT candidate sets (including high-count systems such as dodder’s **>100 genes (2019)**), quantify promoter-element distributions using **GOLEM (2023)** and show whether candidates differ systematically from native genes [7][8].

5) **Improve annotation coverage in non-model eukaryotes to reduce false positives/unknowns.**
   - Success criterion: Demonstrate improved functional assignment rates for candidate HGT genes using non-model annotation tools (2021) plus **LLM+KG gene-function prediction (2024)** relative to baseline pipelines [11][6].

6) **Organellar (mitochondrial) HGT validation with provenance-aware assembly checks.**
   - Success criterion: Re-analyze at least one organellar mosaicism report class (e.g., Amborella-like cases described in plant HGT overview, 2007 (background)) using read-level provenance + contamination assessment in a standardized pipeline (e.g., **hgtseq, 2022**) [9][5].

7) **Systematic surveys of animal mobile-element transfer associated with parasitism.**
   - Success criterion: Extend host–parasite transposon-transfer analyses (2010 (background)) to additional host–vector pairs using standardized detection and explicitly report how alternative explanations (shared ancestry/paralogy) are excluded [10][4].

8) **Quantitative, comparable reporting of HGT “counts” and uncertainty across studies.**
   - Success criterion: For each genome-wide study, report candidate numbers (like the **57 gene families, 2012** plant case) together with uncertainty categories tied to specific confounders (contamination, paralogy, gene loss) [1][4][5].

## 7. Implications & Next‑Step Recommendations
1) **(0–3y) Make contamination-aware HGT screening standard in eukaryotic genome projects using hgtseq (2022).** Why now: contamination is a dominant systematic that can masquerade as HGT, and hgtseq explicitly incorporates contamination assessment [5].

2) **(0–3y) Establish shared benchmarks and reporting standards for eukaryotic HGT claims.** Why now: lack of benchmarks limits sensitivity/specificity comparisons and leaves phylogenetic incongruence vulnerable to confounders (gene loss/paralogy) [4][5].

3) **(0–3y) Prioritize functional annotation improvements for non-model taxa using updated annotation tooling (2021) plus LLM+KG approaches (2024).** Why now: annotation bottlenecks directly limit interpretation and can inflate false positives or leave candidates uninterpretable [11][6].

4) **(3–10y) Integrate regulatory-element evidence into plant HGT validation using GOLEM (2023) and cross-species expression models such as DeepPlantCRE (2025).** Why now: regulatory integration is a key uncertainty for retention/impact, and these tools directly target promoter/motif structure and cross-species generalization [8][14].

5) **(3–10y) Expand from case studies to systematic, ecology-stratified surveys in high-opportunity systems (parasitic plants; host–parasite animal interfaces).** Why now: intimate biological interactions are repeatedly implicated (dodder >100 genes in 2019; host–parasite transposon transfer in 2010 (background)), but systematic comparisons are limited by confounders that standardized pipelines and benchmarks can mitigate [7][10][5].

## References
1. [Richards et al., 2012, Widespread impact of horizontal gene transfer on plant colonization of land](doi:10.1038/nature11152)
2. [Altincicek et al., 2011, Horizontally transferred fungal carotenoid genes in the two-spotted spider mite Tetranychus urticae](https://pmc.ncbi.nlm.nih.gov/articles/PMC3297373/) (background)
3. [Dunning Hotopp et al., 2009, Lateral gene transfer between prokaryotes and multicellular eukaryotes: ongoing and significant?](doi:10.1186/1741-7007-7-20) (background)
4. [Keeling & Palmer, 2008, Horizontal gene transfer in eukaryotic evolution](doi:10.1038/nrg2386) (background)
5. [Gomez et al., 2022, hgtseq: A Standard Pipeline to Study Horizontal Gene Transfer](https://pmc.ncbi.nlm.nih.gov/articles/PMC9738810/)
6. [Sunil et al., 2024, The gene function prediction challenge: large language models and knowledge graphs to the rescue](https://arxiv.org/pdf/2408.07222.pdf)
7. [Parasitic plants use stolen genes to make them better parasites](https://www.psu.edu/news/research/story/parasitic-plants-use-stolen-genes-make-them-better-parasites) (background)
8. [Nevosád et al., 2023, GOLEM: distribution of Gene regulatOry eLEMents within the plant promoters](https://arxiv.org/pdf/2310.15206.pdf)
9. [Richardson & Palmer, 2007, Horizontal gene transfer in plants](https://pubmed.ncbi.nlm.nih.gov/17030541/) (background)
10. [Gilbert & Feschotte, 2010, A role for host-parasite interactions in the horizontal transfer of transposons](https://pubmed.ncbi.nlm.nih.gov/20428170/) (background)
11. [Galchenkova & Korzhenkov, 2021, Modern tools for annotation of small genomes of non-model eukaryotes](https://arxiv.org/pdf/2102.04058.pdf) (background)
12. [Zoller et al., 2021, Eukaryotic gene regulation at equilibrium, or non?](https://arxiv.org/pdf/2110.06214.pdf) (background)
13. [Cui et al., 2007, MicroRNAs preferentially target the genes with high transcriptional regulation complexity](https://arxiv.org/pdf/q-bio/0701001.pdf) (background)
14. [Wu et al., 2025, DeepPlantCRE: A Transformer-CNN Hybrid Framework for Plant Gene Expression Modeling and Cross-Species Generalization](https://arxiv.org/pdf/2505.09883.pdf)
15. [Beyond Agrobacterium-Mediated Transformation: Horizontal Gene Transfer from Bacteria to Eukaryotes](https://pmc.ncbi.nlm.nih.gov/articles/PMC9473684/) (background)
