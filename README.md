# Memo
## Week 1: Overview

Key scientific question (KSQ), quoted from [F1L Internship Emulator Week 1](https://www.linkedin.com/pulse/week-1-f1l-internship-emulator-ksq-dean-lee-354ke/):
> Using available scRNA-seq data from cancer cell lines, how would you explore the use of the following FDA-approved antibody therapies in additional cancers?
> - Trastuzumab: Targets HER2 and is used in the treatment of HER2-positive breast and gastric cancers.
> - Bevacizumab: Targets VEGF and is used for a variety of cancers, including colorectal, lung, glioblastoma, breast, liver, and kidney cancer.

### What is single cell RNA-seq (scRNA-seq)?
Given a collection of cells, scRNA-seq is generally able to do the following for each cell: sequence each captured RNA transcript from the cell's transcriptome and associate those sequenced transcripts with that cell (Jovic et al. 2022). Some example applications of scRNA-seq include: understanding the diversity of gene expression cells within a sample/environment (sample heterogeneity), determining how cell behavior varies spatio-temporally (for example, different parts of a tumor responding to oxygen access or drug exposure), comparing expression patterns of cell types (for example, compare immune vs blood vs neuron), discovering rare individual cells in a population (for example, hyper-resistant cancer cells), and tracing lineages of cells (tracking line of parental cells to progenitor cell(s)) (Haque et al. 2017).


[//]: # (COMMENTS IN MARKDOWN: https://stackoverflow.com/questions/4823468/comments-in-markdown)
[//]: # (### How can scRNA-seq be used for our KSQ?)

### What are cancer cell lines?
Cancer cell lines are cultures of cancer cells that have been taken from patients or animals and characterized based on many things such as: what part of the body their taken from, major malfunctioning/mutated pathway(s) and genes, malignancy, and more. Cancer cell lines are useful due to their ability to provide infinite biological material for *in vitro* experimentation (provided the right conditions are met) while mostly retaining their original genomic identity if the proper controls are in place (Mirabelli et al. 2019). Hence, they are one of the most common models for cancer drug development and testing ([CCLE](https://sites.broadinstitute.org/ccle/)).

- For understanding basics of a particular cancer, try looking at Wiki and [Cancer.gov](https://www.cancer.gov/).
- For understanding cancer cell lines from a purely data, try Cancer Cell Line Encyclopedia, [CCLE](https://sites.broadinstitute.org/ccle/).

[//]: # (### How can cancer cell lines be used for cancer drug development?)

### What are antibody therapies, and how are they related to cancer treatment?

Antibody therapies utilize antibodies to treat disease ([Cancer.gov](https://www.cancer.gov/publications/dictionaries/cancer-terms/def/antibody-therapy)). Antibodies are proteins made by the immune system that bind to specific antigens. Antigens are any substance that causes an immune response against itself. 

#### Monoclonal antibodies (mAb) vs Polyclonal antibodies (pAb)
Monoclonal antibody (mAb) preparations are distinct from polyclonal antibody (pAb) preparations. Cloning is making identical copies of a cell. "Mono" clonal means one cloning, thus mAb are many copies of a single antibody molecule made to target specific antigens, produced by cloning a single parent, immune cell ([National Research Council](https://www.ncbi.nlm.nih.gov/books/NBK100188/)). "Poly" clonal means multiple cloning thus, pAb are a mixture consisting of a variety of types antibodies derived from multiple parent, immune cells ([genscript.com](https://www.genscript.com/polyclonal_or_monoclonal.html#:~:text=In%20contrast%20to%20polyclonal%20antibodies,antigen%20and%20is%20extremely%20specific.)). As of 2024, antibody therapies are synonymous with mAb therapies, there are no pAb therapies on the market (The Antibody Society 2024), but that may change in the future (Wang et al. 2013).

#### Antigen Specificity
Most FDA approved mAb are mono-specific, meaning they recognize only a single epitope of an antigen, but some approved mAb's are di-specific (The Antibody Society 2024). Poly-specific antibody research is promising (Runcie et al. 2018; [FDA article](https://www.fda.gov/drugs/spotlight-cder-science/bispecific-antibodies-area-research-and-clinical-applications)). 

#### Antibody Therapy Mechanisms of Action 
1. Some antibody therapies are immunotherapies, meaning they help improve the immune response against the disease by recruiting the immune system to the target. 
2. Others are used to deliver drugs to target molecules.
3. Some stop/affect some key function supporting the cancer cell growth. 
4. Some antibody therapies fit more than one of these mechanisms of action.

See Cancer.gov's [antibody therapy](https://www.cancer.gov/publications/dictionaries/cancer-terms/def/antibody-therapy) and [monoclonal antibodies](https://www.cancer.gov/about-cancer/treatment/types/immunotherapy/monoclonal-antibodies), and [mayoclinic.org](https://www.mayoclinic.org/diseases-conditions/cancer/in-depth/monoclonal-antibody/art-20047808).

#### Use in Cancer
As of 2024, a large majority of antibody therapies on the market are for cancer treatment (The Antibody Society 2024). Antibody therapies have become increasingly popular for treating cancer due to their increased specificity over small molecules via protein engineering (Shepard et al. 2017). Antibody therapies have less off-target effects.

### How does Trastuzumab work?
HER2 is a proto-oncogene that encodes a transmembrane receptor protein that is structurally similar to the epidermal growth factor receptor (EGFR) protein (Herceptin 2024, see "Mechanism of Action" and "Description"). Proto-oncogenes are genes that are responsible for processes that prevent cancer, and become oncogenes when mutated (perpetuate cancer). Herceptin is the brand name of a drug using Trastuzumab as an active ingredient. Trastuzumab is a mAb that has been shown to preferentially inhibit proliferation of cells over-expressing HER2 (over normal cells) by mediating antibody-dependent cellular cytotoxicity (ADCC). ADCC is an immune response where an effector immune cell kills a target cell that has been identified by an antibody ([wiki](https://en.wikipedia.org/wiki/Antibody-dependent_cellular_cytotoxicity)); this means Trastuzumab uses mechanism of action 1 described above.

HER2-positive breast and gastric cancers can be treated using Trastuzumab (Greenblatt & Khaddour 2024; Herceptin 2024, Section 14 "Clinical Studies").

### How does Bevacizumab work?
Bevacizumab is a mAb that binds the paracrine signaling protein vascular endothelial growth factor (VEGF) then prevents VEGF to intended endothelial cell surface receptors Fl1-1 and KDR
(Bevacizumab 2022, see "Mechanism of Action" and "Description"). VEGF binding its receptors causes endothelial cell proliferation and formation of new blood vessels according to angiogenesis models. Therefore, Bevacizumab uses mechanism of action 3 described above.

Bevacizumab can be used to treat a variety of cancers, including: cervical cancer, metastatic colorectal cancer, non-squamous non-small cell lung cancer, ovarian, glioblastoma, and more
(Gerriets & Kasi 2023; Bevacizumab 2022, Section 14 "Clinical Studies")

### Paraphrasing the KSQ
- The KSQ of this work is: how can we use open source, scRNA-seq data collected from a variety of cancer cell lines to determine the effectiveness of FDA approved antibody therapies Trastuzumab and Bevacizumab to treat other types of cancer the therapies have not yet been approved? 
- How can we use transcriptome data from different cancer cell types and knowledge of Trastuzumab and Bevacizumab mechanisms and molecular targets to identify other cancers that may be worth exploring as clinical targets?
    - Given their mono-specificity and monoclonal nature, we are probably looking for single molecular targets rather than multiple at once (though some cancers may possess multiple)

### Remaining Questions
- Where can we get "open source, scRNA-seq data collected from a variety of cancer cell lines"? CCLE?
- What kind of cancers should I expect to behave like the ones treated by Trastuzumab and Bevacizumab?
    - Obvious starting point: find cancers with VEGF and/or HER2 over-expression. 
    - Is it possible to find cancers with similar expression profiles to the cancers treated by Trastuzumab and Bevacizumab, but do not over-express VEGF or HER2?
- Can we utilize knowledge about the monoclonal, mono-specific, and/or mechanistic (mechanism of action) nature of the drugs with scRNA-seq to match potential additional cancers with the drugs, or does that require some additional information (like incorporating antibody protein structure knowledge in molecular dynamic simulations)?
- What kind of (statistical) analysis on the scRNA-seq data will help determine that Trastuzumab and/or Bevacizumab might on a given cancer cell line?
    - One sanity check is to make sure that the analysis shows that the cancers *we know Trastuzumab and Bevacizumab **are** effective on* are **confirmed** by our analysis (and similarly for cancers that we know they are not effective on).

## Week 2: The Paper
Details for this week can be found at [F1L Internship Emulator Week 2](https://www.linkedin.com/pulse/week-2-f1l-internship-emulator-paper-dean-lee-3crce/)

### Summary

#### What did they do?
##### Figures 1-2
They took various cell lines from CCLE, and performed scRNA-seq on them in pools (mixtures of cells from various cell lines). Then, they used the consensus of two methods to assign cells from the pools to their respective cell lines, and threw out ones that did not meet consensus or failed other QC requirements. Then, within each of the cell lines they performed dimesnional reduction then clustering to identify if the cell line had distinct subpopulations and, if so, how many subpopulations. If subpopulations were present, they explored them. Across all cell lines (regardless of subpopulation presence) they did various types of analyses to identify recurrent heterogeneous programs (RHPs) - RHPs are sets of genes that showed significant correlation and variation between cells within a cell line, and consistently varied across multiple cell line. Correlation defines heterogeneity patterns: groups of genes that tend to vary together when comparing groups of cells against other groups of cell (a group would generally be one subpopulation vs another subpopulation of cells, or one cell line vs another cell line, or perhaps even one subpopulation of a cell line vs a subpopulation of a different cell line).

The authors then categorized RHPs based on whether they or not they were associated with cell cycle. They found 2 cell cycle RHPs, and 10 non-cell cycle RHPs. 

##### Figures 3-7
For multiple of the cancer cell lines, they performed further analysis by pooling real tumor cells with cell line cells then performing scRNA-seq on these to compare the expression profiles of the two. Most of the paper is devoted to exploring if RHPs *in vitro* (cancer cell lines) follow similar variation patterns *in vivo* (real tumors).

[//]: # (various analyses on their expression profiles - hierarchical clustering, non-negative matrix factorization -)

#### Why did they do it? (Kinker et al's goal)
The authors set out to discern if cancer cell lines adequately capture the cellular heterogeneity observed in real tumors.

#### What did they learn?
Most of the results in the paper describe how the RHPs successfully reflect real intratumor heterogeneity (ITH). The authors argue that as cancer genetics focuses on mutations recurrent across cancers - since these mutations are proposed to drive cancer formation - so should cancer transcriptomics focus on RHPs across cancers - since these programs define cancer phenotypes.

### Reflective Questions

#### How did the authors handle the potential caveat of co-culturing cell lines before profiling by scRNA-seq? Why do you think that caveat was or was not adequately addressed?
The caveat is that for the predefined pools from CCLE (but not the custom pool of HNSCC), the cells were co-cultured for 3 days before profiling by scRNA-seq. The concern is that this would give a false representation of the transcriptome of the cell lines since there would be multiple types of cancer present in a single tube for multiple days - which is generally not reflective of real tumors.

The authors gave two answers to handle this caveat. 
1. They established that heterogeneity patterns between cell lines in a pool were as similar as patterns between cell lines from different pools (they cite Supplementary Fig. 1b). Since the heterogeneity patterns showed consistent amounts of similarity to cells they were co-cultured with and cells they were not co-cultured with, the co-culturing likely had no effect on their expression. 
2. The authors performed an experiment for six cell lines. For each, they prepared a 3 day co-culture and a 0-day co-culture then profiled each by scRNA-seq. The results showed a small effect on the average gene expression of each cell line, and more importantly the heterogeneity patterns within a cell line were very much the same between the two group (they cite Supplementary Fig. 1c–f).

I think that they did adequately address this concern. Their first answer is a clever way to use data they already generated to try to address the concern, and at have sound logic at face-value. But, if this were given alone, I might be concerned that some confirmation bias is at play, since most of their pools had the 3d co-culturing maybe most of the co-cultures experienced an accidental change in expression - such that they all appear to have similar heterogeneity patterns - which may not be detectable/apparent since their experiment is not designed to measure co-culture effect. However, the authors avoid my concern by performing a reasonable experiment on a small subset of the cells that is designed to measure whether co-culture does or does not affect a cell line's expression profile.

#### The authors identified discrete subpopulations of cells within a subset of individual cell lines (Fig. 2A-B). What might be the reason why some cell lines have these discrete subpopulations while others do not?
One reason could be that cell some cell lines show largely continuous variation across cells, causing one big clustering of cells that makes identifying subpopulations very difficult (see Figure 2a, left/blue population - imagine a cell line where this was the only type of variation seen and there's no discrete subpopulation); conversely, if a cell line shows largely discontinuous variation at any point, this will result in one or more discrete populations. Another reason could be some cancer cell lines have less, unstable, genetic variation within them (perhaps due to the underlying mutation(s) driving the cancer), such that the cells end up in one relatively tight cluster; conversely, cell lines with more unstable genetic mutations will tend to accumulate mutations and are more likely to spawn rare mutants that show distinct variability in expression and thus have distinct subpopulations.

#### What are RHPs and how were they defined?
See definition of RHPs in "What did they do?" above.

RHPs were identified by apply non-negative matrix factorization (NMF) to the scRNA-seq data matrix associated with each cell line. The clusters can be obtained by querying the columns of H following NMF factorization for clustering (V=WH, see [Wiki](https://en.wikipedia.org/wiki/Non-negative_matrix_factorization#Clustering_property)). Comparing clusters with similar genes across cell lines then taking the consensus of those comparisons revealed RHPs.

#### How do the identified RHPs relate to in vivo programs of heterogeneity in tumors, and what evidence supports this relationship?
For the most part, RHPs *in vitro* and programs *in vivo* appeared to be highly consistent with each other. That is, cancer cell lines RHPs were generally found to successfully recapitulate the heterogeneity found in real tumors. The authors identified 12 RHPs in total - 2 cell cycle programs and 10 non-cell cycle programs. 

For the 2 cell cycle RHPs, they found that the G2/M programs were consistent between cancer cell lines and real tumors, but G1/S programs showed some differences between *in vitro* (cell lines) and *in vivo* (real tumor) instances of those programs (see pg 1209). 

For the 10 non-cell cycle programs, the programs labeled 9 and 10 were the only ones identified *in vitro* that did not have a corresponding *in vivo* program, which the authors propose might be a lack of *in vivo* data (see pg 1210). The authors surmised that 7 of the 10 *in vitro* RHPs showed significant similarity to the *in vivo* RHPs (they cite Fig. 4a, see pg 1210). This was based on similarity between *in vivo* RHP data and *in vitro* RHP data, some RHPs which were previously defined and others which the authors derived from available scRNA-seq data on real tumors. Additional verification was done for many of the RHPs by performing scRNA-seq on samples containing both real tumor cells and cancer cell line cells, which often resulted in indistinguishable expression patterns.

#### Where can you download the scRNA-seq data as shown in Figure 1B?
See the "Data availability" section. They give two links, one of which is a "Study" on CCLE: https://singlecell.broadinstitute.org/single_cell/study/SCP542/pan-cancer-cell-line-heterogeneity. The other is from GEO under accession GSE157220: https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE157220

## Week 3: The Data

### Notes to self
1. Freshly installed WSL (to use Unix on Windows) with Ubuntu distribution: https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode
2. Freshly installed Anaconda for Linux (Debian, x86 arch)
    - https://freelearning.anaconda.cloud/get-started-with-anaconda
        - except I did not go with the Anaconda Navigator GUI, I used the link below
    - https://docs.anaconda.com/anaconda/install/linux/
3. Downloaded data, see above "Where can you download the scRNA-seq data as shown in Figure 1B?" (**See old version below) In bash terminal type:
```bash
# note 1: click "Bulk Download" to generate this URL.
# note 2: add the -k before "URL from website" if needed for certificate error as suggested
# note 3: ".exe" and "if ($?) { rm cfg.txt } " are Windows powershell specific, I've adjusted the things necessary
curl.exe -k "URL from website"  -o cfg.txt
curl.exe -K cfg.txt
if [ $? -eq 0 ]; then
    rm cfg.txt
fi
```

4. Forked [F1L GitHub](https://github.com/deanslee/FigureOneLab) repo to my Github, then cloned repo to my machine
5. Based on imports in notebooks from Step 4, created F1L emulator conda environment, activated then installed packages as specified in the file "./240703_kinker_explore.ipynb" by running the following commands in Bash shell:
    ```bash
    conda create --name 2024-F1L
    conda install jupyter
    conda install -c conda-forge scanpy python-igraph leidenalg anndata pandas numpy scipy seaborn matplotlib
    ```
6. Followed tutorials on scRNA-seq (*hit some snares, see below, took two different tutorials). This step: briefly look at table of contents and **skim** relevant chapters from [scbp](https://www.sc-best-practices.org/preamble.html)
- scRNAseq intro: chapter 2
- raw data processing: chapter 3
- analysis frameworks: chapter 4
- interoperability: chapter 5 (switching between R's biocounductor/seurat and Python's scanpy)
- pre-processing and visualization: chapters 6-9
- annotation then basic analysis: chapters 10-12

7. (***) Reading scbp chapters 3-4, as I am working on 241101_kinker_anndata.ipynb and 250104_kinker_scanpy.ipynb
- Did [AnnData getting started tutorial](https://anndata.readthedocs.io/en/latest/tutorials/notebooks/getting-started.html) (which is the same as [scbp 4.2 code along](https://www.sc-best-practices.org/introduction/analysis_tools.html#storing-unimodal-data-with-anndata))
- Did [scbp 4.3 code along](https://www.sc-best-practices.org/introduction/analysis_tools.html#unimodal-data-analysis-with-scanpy)
- Reviewed [10 min to pandas tutorial](https://pandas.pydata.org/docs/user_guide/10min.html#min) 
- To get the data into an AnnData object, I followed a different process than original notebook. On my computer, DataFrames proved to be too slow for the counts matrix, so I stayed in numpy for that part of the code. Because the counts was made a dataframe in the original notebook, I had to adjust how to mask out invalid CellIDs (that aren't in the meta data but are in the UMI counts matrix) with some finagling of dataframe operations. 
- Thought I completed notebook around 02JAN25. When I came back later, found the UMAP plot was incorrect (250104_kinker_scanpy.ipynb) - mixing of different cell types suggests my indexing got off. Corrected 06-07JAN25.
- **Moral of story:** be very careful when indexing your single cell count data for AnnData


8. (***) Reading chapters 6-9, as I am working on 250106_kinker_explore.ipynb.
- [scbp 6.2 code along](https://www.sc-best-practices.org/preprocessing_visualization/quality_control.html)


*Original Step 5 was attempting process below. But, Sanbomics scripts kept hitting dependency issues and finally in the second video he mentions using the prepreprocessed AnnData, pp_adata, folder which we did not prepare in the first script. His process works well for him, but was unfortunately not very helpful to me. PROCESS: Followed Sanbomics guide to preprocessing and analyzing scRNA-seq data and skimming relevant chapters from [sc-best-practices](https://www.sc-best-practices.org/preamble.html):
- see my folder on sanbomics tutorial for any note
- raw data processing: Chapters 1-5 of sc-best-practices may be **_prerequisite_** but not covered in video!
- pre-processing: Chapters 6-9 of sc-best-practices with [2024 scRNA-seq tutorial, part 1: Raw data processing](https://www.youtube.com/watch?v=cmOlCTGX4Ik) - like using CellBender to deal with technical covariates
- annotation then basic analysis: Chapters 10-12 of sc-best-practices with [2024 updated single-cell guide - Part 2: RNA Integration and annotation](https://www.youtube.com/watch?v=FqG_O12oWR4)
- PERHAPS LATER: [Complete single-cell RNAseq analysis walkthrough | Advanced introduction (2023 version)](https://www.youtube.com/watch?v=uvyG9yLuNSE)

**Old step 3 code. Although using the CCLE link results in slightly different files than the original F1L notebook's call for, the GEO link is completely different as it gives the raw data, I think.
```bash
curl -o GSE157220_Pool_composition.xlsx "https://ftp.ncbi.nlm.nih.gov/geo/series/GSE157nnn/GSE157220/suppl/GSE157220%5FPool%5Fcomposition.xlsx"; curl -o GSE157220_CPM_data.txt.gz "https://ftp.ncbi.nlm.nih.gov/geo/series/GSE157nnn/GSE157220/suppl/GSE157220%5FCPM%5Fdata.txt.gz"

sudo apt update && sudo apt install pv

pv GSE157220_CPM_data.txt.gz | gunzip > GSE157220_CPM_data.txt
```

*** Code alongs contained in my folder ~/2024-scbp-tutorials

## References
Bevacizumab [Package Insert]. (2022, September 18). Genentech. https://www.accessdata.fda.gov/drugsatfda_docs/label/2022/125085s340lbl.pdf

Gerriets V, Kasi A. Bevacizumab. [Updated 2023 Aug 28]. In: StatPearls [Internet]. Treasure Island (FL): StatPearls Publishing; 2024 Jan-. Available from: https://www.ncbi.nlm.nih.gov/books/NBK482126/

Greenblatt K, Khaddour K. Trastuzumab. [Updated 2024 Jun 22]. In: StatPearls [Internet]. Treasure Island (FL): StatPearls Publishing; 2024 Jan-. Available from: https://www.ncbi.nlm.nih.gov/books/NBK532246/

Haque, A., Engel, J., Teichmann, S. A., & Lönnberg, T. (2017). A practical guide to single-cell RNA-sequencing for biomedical research and clinical applications. Genome medicine, 9, 1-12. https://doi.org/10.1186/s13073-017-0467-4

Herceptin [Package Insert]. (2024, June 18). Genentech. https://www.accessdata.fda.gov/drugsatfda_docs/label/2024/103792s5354lbl.pdf

Jovic, D., Liang, X., Zeng, H., Lin, L., Xu, F., & Luo, Y. (2022). Single‐cell RNA sequencing technologies and applications: A brief overview. Clinical and translational medicine, 12(3), e694. https://doi.org/10.1002/ctm2.694

Kinker, G. S., Greenwald, A. C., Tal, R., Orlova, Z., Cuoco, M. S., McFarland, J. M., ... & Tirosh, I. (2020). Pan-cancer single-cell RNA-seq identifies recurring programs of cellular heterogeneity. Nature genetics, 52(11), 1208-1218. https://doi.org/10.1038/s41588-020-00726-6

Mirabelli, P., Coppola, L., & Salvatore, M. (2019). Cancer cell lines are useful model systems for medical research. Cancers, 11(8), 1098. https://doi.org/10.3390/cancers11081098

National Research Council (US) Committee on Methods of Producing Monoclonal Antibodies. Monoclonal Antibody Production. Washington (DC): National Academies Press (US); 1999. Introduction. Available from: https://www.ncbi.nlm.nih.gov/books/NBK100188/

Runcie, K., Budman, D. R., John, V., & Seetharamu, N. (2018). Bi-specific and tri-specific antibodies-the next big thing in solid tumor therapeutics. Molecular Medicine, 24, 1-15. https://doi.org/10.1186/s10020-018-0051-4

Shepard, H. M., Phillips, G. L., Thanos, C. D., & Feldmann, M. (2017). Developments in therapy with monoclonal antibodies and related proteins. Clinical medicine, 17(3), 220-232. https://doi.org/10.7861/clinmedicine.17-3-220

The Antibody Society. Therapeutic monoclonal antibodies approved or in review in the EU or US. (2024); https://www.antibodysociety.org/resources/approved-antibodies.

Wang, X. Z., Coljee, V. W., & Maynard, J. A. (2013). Back to the future: recombinant polyclonal antibody therapeutics. Current opinion in chemical engineering, 2(4), 405-415. https://doi.org/10.1016/j.coche.2013.08.005

# Miscellaneous Information

## Don't forget the resources on F1L's site!
- 3Blue1Brown for linear algebra
- Points of Significance for statistics
- StatQuest!!! for statistics
- STAT115 by Shirley Liu for an introduction to compbio
- Best practices for scRNA-seq data analysis
- Glittr a collection of Git repos with bioinformatics training material

## The 5 types of human antibodies
See this [resource](https://ruo.mbl.co.jp/bio/e/support/method/antibody-isotype.html#:~:text=Human%20antibodies%20are%20classified%20into,with%20distinct%20characteristics%20and%20roles.&text=IgG%20is%20the%20most%20abundant,of%20human%20immunoglobulins%20(antibodies).)

## Official FDA approved labels resource
- https://labels.fda.gov/
- to access drug labels specifically: link above > "Drugs" Tab > "Drugs@FDA"

## Genome.gov, definition of a transcriptome
- https://www.genome.gov/about-genomics/fact-sheets/Transcriptome-Fact-Sheet
- transcriptome: complete collection of RNA transcripts within a cell, majority of which are mRNA, but may include other RNA types depending on experiment

## Non-negative matrix factorization (NMF)
- overview math, small example, and algorithms to find: https://www.youtube.com/watch?v=TFCgVWNd0mA

## Cell cycle fact
- https://www.sciencefacts.net/cell-cycle.html