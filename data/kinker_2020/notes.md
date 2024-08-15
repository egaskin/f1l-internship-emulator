# Kinker et al. 2020 notes

## What did the authors do? 

### Figures 1-2
They took various cell lines from CCLE, and performed scRNA-seq on them in pools (mixtures of cells from various cell lines). Then, they used the consensus of two methods to assign cells from the pools to their respective cell lines, and threw out ones that did not meet consensus or failed other QC requirements. Then, within each of the cell lines they performed dimesnional reduction then clustering to identify if the cell line had distinct subpopulations and, if so, how many subpopulations. If subpopulations were present, they explored them. Across all cell lines (regardless of subpopulation presence) they did various types of analyses to identify recurrent heterogeneous programs (RHPs) - RHPs are sets of genes that showed significant correlation and variation between cells within a cell line, and consistently varied across multiple cell line. The authors then categorized RHPs based on whether they or not they were associated with cell cycle. They found 2 cell cycle RHPs, and 10 non-cell cycle RHPs. 

### Figures 3-7
For multiple of the cancer cell lines, they performed further analysis by pooling real tumor cells with cell line cells then performing scRNA-seq on these to compare the expression profiles of the two. Most of the paper is devoted to exploring if RHPs *in vitro* (cancer cell lines) follow similar variation patterns *in vivo* (real tumors).

[//]: # (various analyses on their expression profiles - hierarchical clusteri3ng, non-negative matrix factorization -)

## Why did they do it? (Kinker et al's goal)
The authors set out to discern if cancer cell lines adequately capture the cellular heterogeneity observed in real tumors.

## What did they learn?
Most of the results in the paper describe how the RHPs mostly capture the intratumor heterogeneity (ITH). The authors argue that as cancer genetics focuses on mutations recurrent across cancers - since these mutations are proposed to drive cancer formation -so should cancer transcriptomics focus on RHPs across cancers - since these programs define cancer phenotypes.

## Resources
- Cell cycle facts: https://www.sciencefacts.net/cell-cycle.html