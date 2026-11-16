# METHODS

## Single-cell RNA-seq Reanalysis

Published mouse skull and sternum bone marrow scRNA-seq data (GSE313969) were reanalyzed using Seurat.

Following quality-control filtering and doublet removal, data were normalized, scaled, and subjected to principal component analysis (PCA) and graph-based clustering.

CD4-enriched T-cell populations were identified based on lineage-marker expression (*Cd3d⁺, Cd3e⁺, Cd4⁺, Cd8a⁻, Itgam⁻*) and subsetted for re-normalization, PCA, and reclustering.

Cluster-specific marker analysis and Tfh-associated signature scoring (*Pdcd1, Tox, Icos*) were then used to characterize a putative Tfh-like population and compare its distribution between skull and sternum bone marrow.

## Computational Analysis Workflow

```mermaid
flowchart LR
    A["Data acquisition<br/>GSE313969"]
    B["QC & doublet<br/>removal"]
    C["Normalization<br/>PCA & clustering"]
    D["CD4 T-cell<br/>identification"]
    E["CD4 subset<br/>reanalysis"]
    F["Tfh annotation<br/>& signature"]

    A --> B --> C --> D --> E --> F

    style A fill:#173C63,color:#ffffff,stroke:#173C63
    style B fill:#EAF1F8,color:#18283C,stroke:#7895B3
    style C fill:#EAF1F8,color:#18283C,stroke:#7895B3
    style D fill:#EAF1F8,color:#18283C,stroke:#7895B3
    style E fill:#EAF1F8,color:#18283C,stroke:#7895B3
    style F fill:#C23A55,color:#ffffff,stroke:#C23A55
```


---

# RESULTS

## 1. Identification and Distribution of CD4-Enriched T-cell Populations

<table>
<tr>
<td width="50%" valign="top">

### A | Joint CD4 T-cell UMAP

Joint visualization of skull and sternum CD4-enriched T-cell subsets identified distinct transcriptional clusters, including a putative Tfh-like population.

<img src="Fig01_Annotated_Joint_UMAP_Centered.png" width="100%" alt="Annotated joint CD4 T-cell UMAP">

</td>
<td width="50%" valign="top">

### B | UMAP Split by Tissue

Tissue-split visualization using shared UMAP coordinates revealed the distribution of CD4-enriched T-cell populations across skull (701 cells) and sternum (339 cells) bone marrow.

<img src="Fig02_Annotated_Skull_Sternum_Split.png" width="100%" alt="Skull and sternum tissue-split UMAP">

</td>
</tr>
</table>

**Figure A–B.** Joint and tissue-specific UMAP visualization of CD4-enriched T-cell populations from mouse skull and sternum bone marrow.

---

## 2. Identification of Tfh-Associated Transcriptional Features

### C | Tfh-Associated Marker Expression

Cluster-specific marker analysis revealed expression of *Pdcd1*, *Tox*, and *Icos* in the candidate Tfh-like population.

Additional Tfh-associated markers, including *Cxcr5*, *Bcl6*, and *Il21*, and regulatory T-cell markers, including *Foxp3*, *Il2ra*, and *Ctla4*, were assessed to support provisional cell-state annotation.

<p align="center">
  <img src="Fig03_FullCluster_Marker_DotPlot.png" width="95%" alt="Tfh and Treg marker-expression DotPlot">
</p>

**Figure C.** Expression of T-cell lineage, Tfh-associated, and regulatory T-cell markers across the original joint transcriptional clusters. Dot size represents the percentage of cells expressing each gene, while color represents scaled average expression.

The marker-expression profile supports the identification of a putative Tfh-enriched cluster. However, transcriptional marker expression alone does not establish definitive Tfh identity.

---

## 3. Comparative Abundance of Tfh-like Cells

### D | Tfh Cluster Cell Counts in Skull and Sternum BM

The putative Tfh-enriched cluster contained **110 cells in skull BM (15.7% of 701 selected cells)** compared with **35 cells in sternum BM (10.3% of 339 selected cells)**.

These results indicate a higher descriptive abundance of the Tfh-like cluster within the selected skull BM T-cell population.

<p align="center">
  <img src="Fig09_Tfh_Cluster_CellCounts.png" width="70%" alt="Tfh cluster cell counts">
</p>

**Figure D.** Absolute counts of cells assigned to the putative Tfh-enriched cluster in skull and sternum bone marrow.

Percentages are calculated relative to the retained T-cell populations (clusters 1–5), rather than total bone marrow cells.

*The comparison is descriptive; biological-replicate-level statistical significance was not established.*

---

## 4. Published Evidence of B-cell Activation and Humoral Immunity

### E | Germinal-Center-Like B Cells and Experimental Validation

The original study, *Functional role of skull lymphoid structures in CNS immunosurveillance*, identified germinal-center-like (GC-like) B cells and antibody-secreting cells (ASCs) in skull bone marrow.

Published B-cell scRNA-seq analysis revealed developmental and activation-associated B-cell populations, including GC-like B cells, plasmablasts, and plasma cells.

Additional flow-cytometry experiments provided complementary evidence for GC-like B-cell and antibody-secreting populations in skull bone marrow.

Together, these published findings support the involvement of skull bone marrow in local adaptive humoral immune responses.

<p align="center">
  <img src="B-cell.png" width="95%" alt="Published B-cell populations and experimental validation">
</p>

**Figure E.** Published B-cell transcriptional analysis and experimental validation from the original study.

**Source:** Park et al., *Nature* (2026), Figure 2a–f.

[Functional role of skull lymphoid structures in CNS immunosurveillance](https://doi.org/10.1038/s41586-026-10951-4)

*This figure represents evidence from the original publication and is not a newly performed B-cell reanalysis in this project.*

# REFERENCES

**Primary Publication**

Park, J. H., et al. (2026). *Functional role of skull lymphoid structures in CNS immunosurveillance.* Nature.

https://doi.org/10.1038/s41586-026-10951-4

**Mouse T-cell scRNA-seq Dataset**

GEO Accession: **GSE313969**

https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE313969

**Published Mouse B-cell scRNA-seq Dataset**

GEO Accession: **GSE309634**

https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE309634
