<div align="center">

# Seq2Prot

**The viral genome analyst — from raw Sanger sequencing data to clinical drug resistance reports, 3D protein structures, and mutation surveillance**

<br>

<!-- Badges styled like paper-qa / popular GitHub repos -->
<table>
  <tr>
    <td><strong>Language</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.12">
    </td>
  </tr>
  <tr>
    <td><strong>Core</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Biopython-1.86-009688?style=flat-square&logoColor=white" alt="Biopython">
      <img src="https://img.shields.io/badge/NumPy-2.1-4DABF7?style=flat-square&logo=numpy&logoColor=white" alt="NumPy">
      <img src="https://img.shields.io/badge/SciPy-1.14-8CAAE6?style=flat-square&logo=scipy&logoColor=white" alt="SciPy">
      <img src="https://img.shields.io/badge/Pandas-2.2-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas">
    </td>
  </tr>
  <tr>
    <td><strong>Visualization</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Matplotlib-3.9-11557C?style=flat-square&logo=matplotlib&logoColor=white" alt="Matplotlib">
      <img src="https://img.shields.io/badge/OpenPyXL-3.1-239120?style=flat-square&logo=microsoftexcel&logoColor=white" alt="OpenPyXL">
    </td>
  </tr>
  <tr>
    <td><strong>APIs & Data</strong></td>
    <td>
      <img src="https://img.shields.io/badge/NCBI_BLAST-Entrez-34A853?style=flat-square" alt="NCBI">
      <img src="https://img.shields.io/badge/KEGG-REST_API-0969DA?style=flat-square" alt="KEGG">
      <img src="https://img.shields.io/badge/UniProt-REST-004F9F?style=flat-square" alt="UniProt">
      <img src="https://img.shields.io/badge/Reactome-Analysis-009246?style=flat-square" alt="Reactome">
    </td>
  </tr>
  <tr>
    <td><strong>Environment</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat-square&logo=jupyter&logoColor=white" alt="Jupyter">
      <img src="https://img.shields.io/badge/Requests-2.32-2D3748?style=flat-square" alt="Requests">
    </td>
  </tr>
  <tr>
    <td><strong>Status</strong></td>
    <td>
      <img src="https://img.shields.io/badge/Phase-2_Advanced-059669?style=flat-square" alt="Phase 2">
      <img src="https://img.shields.io/badge/Steps-14_Total-7C3AED?style=flat-square" alt="14 Steps">
      <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="MIT License">
    </td>
  </tr>
</table>

<br>

**14 Pipeline Steps · 2 Analysis Phases · Fully Executable · Clinical-Grade Output**

<br>

[🚀 Quick Start](#-quick-start) · [🗺 Pipeline](#-pipeline-overview) · [📊 Visualizations](#-visualizations) · [🧪 Methodology](#-methodology) · [📁 Structure](#-project-structure)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Quick Start](#-quick-start)
- [Pipeline Overview](#-pipeline-overview)
- [Visualizations](#-visualizations)
- [Methodology](#-methodology)

---

## 🔬 Overview

This pipeline performs **comprehensive viral genomic variant analysis** — tracing the cascade from a single nucleotide change through codon alteration, amino acid substitution, protein structural change, pathway disruption, and clinical outcome.

> **A single nucleotide variant has cascading effects**: it changes a codon → alters an amino acid → modifies protein structure → disrupts a biological pathway → potentially causes drug resistance or immune escape. This pipeline traces every layer of that cascade.

```
DNA Variant → Codon Change → AA Substitution → Structural Change → Pathway Impact → Clinical Outcome
     ↑              ↑               ↑                  ↑                 ↑                ↑
  Step 4         Step 5          Step 5            Step 10           Step 7          Step 12
```

### Key Capabilities

| Feature | Description |
|---------|-------------|
| **Sanger → FASTQ** | Convert proprietary sequencing formats to universal FASTQ with Phred quality scores |
| **BLAST Identification** | Automatic virus species identification against NCBI nucleotide database |
| **Smith-Waterman Alignment** | Local alignment with affine gap penalties for sensitive variant detection |
| **Variant Classification** | SNP / MNP / INS / DEL calling with allele frequency estimation |
| **Functional Annotation** | ClinVar, dbSNP, UniProt cross-referencing with impact assessment |
| **Pathway Enrichment** | KEGG + Reactome analysis with Fisher's exact test and FDR correction |
| **Protein Characterization** | UniProt domain mapping, active site identification, PTM overlap analysis |
| **3D Structure Comparison** | RMSD, TM-score, GDT-TS, per-residue deviation via Kabsch alignment |
| **Phylogenetics** | Neighbor-Joining trees with K2P distance and bootstrap confidence |
| **Drug Resistance** | Stanford HIVDB scoring system with clinical resistance level classification |
| **Epitope Analysis** | B-cell/T-cell epitope prediction with vaccine target identification |
| **Mutation Surveillance** | dN/dS ratio, Shannon entropy, temporal trend tracking, emerging variant alerts |

---

## 🚀 Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/your-username/virus-genomic-analyzer.git
cd virus-genomic-analyzer

# 2. Install dependencies
pip install biopython numpy scipy matplotlib pandas openpyxl python-docx requests jupyter

# 3. Run Phase 1 — Variant Discovery (Steps 0–6)
jupyter notebook Virus_Genomic_Variant_Analysis_Beginners_Guide.ipynb

# 4. Run Phase 2 — Advanced Analysis (Steps 7–14)
jupyter notebook Virus_Genomic_Variant_Analysis_Phase2_Beginners_Guide.ipynb
```

> **Note**: All notebooks run with simulated/demo data by default. No external files or API keys required. Set `DEMO_MODE = False` to use real sequencing data.

---

## 🗺 Pipeline Overview

<div align="center">
<img src="assets/pipeline_flow.gif" alt="Pipeline Flow Animation" width="900">
</div>

<br>

<div align="center">
<img src="assets/pipeline_architecture.png" alt="Pipeline Architecture" width="900">
</div>

### Data Flow

```
.ab1 / .scf / .phd / .seq          Raw Sanger sequencing files
         │
    Step 0 ↓ Sanger → FASTQ conversion (BioPython SeqIO, Phred quality)
         │
      .fastq / .fastq.gz            Standard sequencing format
         │
    Step 1 ↓ Quality Control (encoding detection, GC content, filtering)
    Step 2 ↓ BLAST Identification (NCBI BLAST, virus taxonomy filter)
    Step 3 ↓ Reference Genome (NCBI Entrez, GenBank, gene annotation)
    Step 4 ↓ Alignment & Variant Calling (Smith-Waterman, SNP/MNP/INS/DEL)
    Step 5 ↓ Functional Annotation (ClinVar, dbSNP, UniProt, impact assessment)
    Step 6 ↓ Basic Reports (XLSX with charts + DOCX narrative)
         │
    ──────── Phase 1 Complete ────────
         │
    Step  7 ↓ Pathway Enrichment (KEGG, Reactome, Fisher's exact test, FDR)
    Step  8 ↓ Comprehensive Reports (multi-sheet XLSX + embedded graphs)
    Step  9 ↓ Protein Finding (UniProt domains, active sites, PTMs)
    Step 10 ↓ 3D Structure Prediction (RMSD, TM-score, per-residue deviation)
    Step 11 ↓ Phylogenetic Analysis (NJ tree, bootstrap, clade assignment)
    Step 12 ↓ Drug Resistance (Stanford HIVDB scores, clinical recommendations)
    Step 13 ↓ Epitope Analysis (B-cell/T-cell epitopes, vaccine targets)
    Step 14 ↓ Mutation Surveillance (dN/dS, Shannon entropy, emerging variants)
         │
    ──────── Phase 2 Complete ────────
         │
         ↓ Final Outputs: XLSX + DOCX + Trees + 3D Structures + Clinical Reports
```

<div align="center">
<img src="assets/data_flow.png" alt="Data Flow Diagram" width="900">
</div>

---

## 🔍 Phase 1: Variant Discovery (Steps 0–6)

### Step 0: Sanger → FASTQ Conversion

**Idea**: Raw Sanger sequencing instruments produce proprietary binary formats (`.ab1`, `.scf`). This step converts them to the universal FASTQ format, preserving Phred quality scores that quantify base-calling confidence.

```
.ab1 file (binary)  →  BioPython SeqIO  →  .fastq (text, 4 lines per read)
                         │
                    Phred quality: ASCII(char) - 33 = Q score
                    Q30 = 99.9% accuracy, Q40 = 99.99% accuracy
```

**Key parameters**: `Phred+33` encoding (Sanger/Illumina 1.8+), default quality assignment for formats without quality data.

---

### Step 1: FASTQ Quality Control

**Idea**: Before analysis, verify data quality. Wrong quality encoding (Phred+33 vs Phred+64) leads to incorrect filtering and false variant calls. Auto-detection of encoding scheme prevents systematic errors.

**Key statistics**: Mean quality per read, GC content, N content, read length distribution, quality encoding auto-detection.

---

### Step 2: Virus Identification via BLAST

**Idea**: The virus species is unknown a priori. BLAST compares sequencing reads against the entire NCBI nucleotide database to identify the species, returning taxonomy, E-value, and alignment coordinates.

**Key parameters**: E-value threshold (`0.001`), virus taxonomy filter (`txid10239`), `hit_start`/`hit_end` for genomic region identification.

---

### Step 3: Reference Genome & Gene Annotation

**Idea**: To detect variants, a reference genome is needed for comparison. NCBI Entrez retrieves the reference sequence plus gene annotations (CDS, gene name, product, protein translation) that provide the framework for functional interpretation.

---

### Step 4: Alignment & Variant Calling

**Idea**: Align each read to the reference genome using Smith-Waterman local alignment, then identify positions where the read differs from the reference. Variant calling classifies each difference by type.

**Key parameters**:

| Parameter | Default | Effect When Increased |
|-----------|---------|----------------------|
| Match score | +2 | Stricter alignment (fewer mismatches tolerated) |
| Mismatch penalty | -3 | Fewer mismatches accepted |
| Gap open penalty | -5 | Fewer gaps (prefers mismatches over indels) |
| Gap extend penalty | -2 | Shorter indels |
| Min allele frequency | 0.05 | Fewer variants (high confidence only) |

**Variant types**: SNP (single nucleotide), MNP (multiple nucleotide), INS (insertion), DEL (deletion).

<div align="center">
<img src="assets/variant_distribution.png" alt="Variant Distribution" width="500">
</div>

---

### Step 5: Functional Annotation

**Idea**: A DNA position change is meaningless without biological context. Each variant is annotated with: gene, codon change, amino acid change, clinical significance (ClinVar), population frequency (dbSNP), and protein impact (UniProt).

---

### Step 6: Report Generation

**Idea**: Generate professional reports — XLSX for data analysis (color-coded, auto-filtered, with charts) and DOCX for clinical reading (narrative format, methodology appendix).

---

## 🧬 Phase 2: Advanced Analysis (Steps 7–14)

### Step 7: Pathway Enrichment Analysis

**Idea**: Individual variants affect genes, but genes work together in biological pathways. Enrichment analysis asks: **"Are variant-affected genes concentrated in certain pathways more than expected by chance?"** This reveals functional patterns invisible at the single-gene level.

**Statistical framework**: Fisher's exact test on a 2×2 contingency table, followed by multiple testing correction (Benjamini-Hochberg FDR).

<div align="center">
<img src="assets/enrichment_chart.png" alt="Pathway Enrichment" width="750">
</div>

**Why it matters**: Finding that 3/4 genes in the "Viral genome replication" pathway have variants (enrichment ratio 2.25×, FDR p=0.028) reveals the virus may have altered its replication strategy — something invisible when looking at individual genes.

---

### Step 8: Comprehensive Excel Reports with Graphs

**Idea**: Phase 2 reports expand beyond basic variant data. Multi-sheet XLSX workbooks include pathway enrichment sheets, protein impact sheets, and embedded charts (pie charts, bar charts, heatmaps) with color coding and auto-filters.

**Report structure**: 8 sheets (Summary, All Variants, Pathway Enrichment, Protein Impact, Pathogenic, Novel, Gene Map, Methodology).

---

### Step 9: Protein Finding & Characterization

**Idea**: DNA variants change amino acids. This step determines **WHERE** in the protein the change occurs — functional domain? Active site? Binding site? Post-translational modification site? The location determines the biological impact.

**Impact assessment**:

| Location | AA Change Type | Impact Level |
|----------|---------------|-------------|
| Active/binding site | Any | **HIGH** |
| Functional domain | Radical (e.g., R→P) | **HIGH** |
| Functional domain | Conservative (e.g., I→L) | **MODERATE** |
| Outside domain | Radical | **MODERATE** |
| Outside domain | Conservative | **LOW** |

---

### Step 10: 3D Structure Prediction & Comparison

**Idea**: Protein function depends on 3D shape. If a variant changes the shape, function may be altered. This step predicts structures for both wild-type and variant proteins, then quantifies the difference.

**Key metrics**:

| Metric | Formula | Interpretation |
|--------|---------|----------------|
| **RMSD** | √(Σ‖pᵢ − qᵢ‖² / N) | < 2Å = similar, > 4Å = different conformation |
| **TM-score** | Length-normalized similarity | > 0.5 = same fold, < 0.3 = different fold |
| **GDT-TS** | %(≤1Å) + %(≤2Å) + %(≤4Å) + %(≤8Å) | > 80 = high accuracy |
| **Per-residue deviation** | Distance at each Cα | Identifies **WHERE** the change is |

<div align="center">
<img src="assets/structure_deviation.png" alt="3D Structure Comparison" width="800">
</div>

---

### Step 11: Phylogenetic Analysis

**Idea**: Place the identified virus strain in its evolutionary context. Which clade does it belong to? How related is it to other strains? Are the variants shared across lineages? Phylogenetic analysis answers these questions.

**Method**: Neighbor-Joining tree with Kimura 2-parameter distance correction and bootstrap confidence assessment.

<div align="center">
<img src="assets/phylogenetic_tree.png" alt="Phylogenetic Tree" width="750">
</div>

---

### Step 12: Drug Resistance Analysis

**Idea**: Some variants directly confer resistance to antiviral drugs. By matching variant positions against known resistance databases (Stanford HIVDB), the pipeline predicts which drugs will be ineffective for a given viral strain.

**Scoring system** (Stanford HIVDB):

| Score | Level | Clinical Meaning |
|-------|-------|-----------------|
| 0–9 | Susceptible | Drug works normally |
| 10–14 | Potential low-level | Minor concern |
| 15–29 | Low-level | Some reduction in efficacy |
| 30–59 | Intermediate | Significant reduction |
| ≥ 60 | High-level | Drug likely ineffective |

<div align="center">
<img src="assets/drug_resistance.png" alt="Drug Resistance Profile" width="800">
</div>

---

### Step 13: Epitope Analysis & Vaccine Targets

**Idea**: The immune system recognizes viral proteins through epitopes (short peptide regions). If a variant falls within an epitope, the virus may escape immune recognition. This step predicts epitopes and checks for variant overlap to identify vaccine targets and immune escape risks.

**Prediction methods**:
- **B-cell epitopes**: Hydrophilicity + flexibility scoring (surface-exposed regions)
- **T-cell epitopes (MHC-I)**: 9-mer peptide binding motif analysis
- **Conservation analysis**: Highly conserved epitopes make better vaccine targets

<div align="center">
<img src="assets/epitope_map.png" alt="Epitope & Domain Map" width="800">
</div>

---

### Step 14: Mutation Surveillance & Temporal Analysis

**Idea**: Viruses evolve in real-time. Tracking how mutation frequencies change over time detects emerging variants before they become dominant. This step provides early warning for public health response.

**Key analyses**:

| Analysis | Method | Interpretation |
|----------|--------|----------------|
| **dN/dS ratio** | Non-synonymous / Synonymous rate | < 1 = purifying selection, > 1 = positive selection |
| **Shannon entropy** | -Σ pᵢ log₂(pᵢ) per position | Higher = more diverse = more variation |
| **Growth rate** | Δ frequency / Δ time | > 10%/quarter = emerging variant |
| **Emerging variant detection** | Growth rate threshold | Alerts for mutations increasing rapidly |

<div align="center">
<img src="assets/surveillance_dashboard.png" alt="Mutation Surveillance Dashboard" width="900">
</div>

---

## 📊 Visualizations

<div align="center">

### Pipeline Flow Animation
<img src="assets/pipeline_flow.gif" alt="Pipeline Flow" width="900">

### Pipeline Architecture
<img src="assets/pipeline_architecture.png" alt="Pipeline Architecture" width="900">

### Data Flow Diagram
<img src="assets/data_flow.png" alt="Data Flow" width="900">

### Variant Type Distribution
<img src="assets/variant_distribution.png" alt="Variant Distribution" width="500">

### Pathway Enrichment
<img src="assets/enrichment_chart.png" alt="Enrichment Analysis" width="750">

### 3D Structure Deviation
<img src="assets/structure_deviation.png" alt="Structure Deviation" width="800">

### Drug Resistance Profile
<img src="assets/drug_resistance.png" alt="Drug Resistance" width="800">

### Phylogenetic Tree
<img src="assets/phylogenetic_tree.png" alt="Phylogenetic Tree" width="750">

### Epitope & Domain Map
<img src="assets/epitope_map.png" alt="Epitope Map" width="800">

### Mutation Surveillance Dashboard
<img src="assets/surveillance_dashboard.png" alt="Surveillance Dashboard" width="900">

</div>

---

## 🧪 Methodology

### Statistical Methods

| Method | Step | Purpose |
|--------|------|---------|
| **Phred quality scoring** | 0–1 | Base-calling confidence (Q = -10×log₁₀(P_error)) |
| **Smith-Waterman alignment** | 4 | Local sequence alignment with affine gap penalties |
| **Fisher's exact test** | 7 | Pathway enrichment significance (2×2 contingency table) |
| **Benjamini-Hochberg FDR** | 7 | Multiple testing correction for pathway analysis |
| **Bonferroni correction** | 7 | Conservative alternative for multiple testing |
| **Kabsch algorithm (SVD)** | 10 | Optimal protein structure superposition (rotation/translation) |
| **Neighbor-Joining** | 11 | Phylogenetic tree construction from distance matrix |
| **Kimura 2-parameter** | 11 | Nucleotide substitution distance (Ti/Tv correction) |
| **Bootstrap resampling** | 11 | Confidence assessment for tree topology |
| **Shannon entropy** | 14 | Per-position sequence diversity measurement |
| **dN/dS ratio** | 14 | Detection of natural selection pressure |

### Key Thresholds

| Threshold | Value | Meaning |
|-----------|-------|---------|
| Quality score (Phred) | Q30 | 99.9% base-calling accuracy |
| BLAST E-value | 0.001 | 0.1% chance of random match |
| Enrichment p-value | 0.05 (FDR) | 5% of discoveries are false positives |
| RMSD significance | 2.0 Å | Above = notable structural change |
| TM-score fold threshold | 0.5 | Above = same protein fold |
| Bootstrap confidence | 70% | Above = moderate-to-strong tree support |
| Drug resistance | Score ≥ 60 | High-level resistance |
| Emerging variant | Growth > 10%/quarter | Rapidly increasing mutation |

### External Databases & APIs

| Resource | Purpose | Access Method |
|----------|---------|---------------|
| [NCBI BLAST](https://blast.ncbi.nlm.nih.gov/) | Virus species identification | `Bio.Blast.NCBIWWW` |
| [NCBI Entrez](https://www.ncbi.nlm.nih.gov/books/NBK25501/) | Genome & annotation retrieval | `Bio.Entrez` |
| [KEGG REST API](https://www.kegg.jp/kegg/rest/keggapi.html) | Pathway database queries | HTTP REST |
| [Reactome](https://reactome.org/) | Pathway enrichment analysis | HTTP REST |
| [UniProt](https://www.uniprot.org/) | Protein annotations & domains | HTTP REST |
| [RCSB PDB](https://www.rcsb.org/) | 3D protein structures | HTTP REST |
| [Stanford HIVDB](https://hivdb.stanford.edu/) | Drug resistance mutations | Reference data |
| [IEDB](https://www.iedb.org/) | Immune epitope database | Reference data |
---

## ⚠️ Important Notes

- **NCBI API**: Requires email (`NCBI_EMAIL`) and optional API key (`NCBI_API_KEY`) for higher rate limits
- **Demo mode**: All notebooks run with simulated data by default — no external data needed
- **Rate limiting**: KEGG, Reactome, and NCBI APIs have rate limits (~1 request/second)
- **Memory**: Large datasets (>10,000 variants) may require chunked processing
- **3D structures**: Real structure prediction requires AlphaFold2 or ColabFold (GPU recommended)

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

[⬆ Back to Top](#-virus-genomic-variant-analysis-pipeline)

</div>

