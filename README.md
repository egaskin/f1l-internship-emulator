# Memo
## Week 1: Overview

Key scientific question (KSQ) (directly quoted from [F1L Internship Emulator Week 1](https://www.linkedin.com/pulse/week-1-f1l-internship-emulator-ksq-dean-lee-354ke/))
> Using available scRNA-seq data from cancer cell lines, how would you explore the use of the following FDA-approved antibody therapies in additional cancers?
> - Trastuzumab: Targets HER2 and is used in the treatment of HER2-positive breast and gastric cancers.
> - Bevacizumab: Targets VEGF and is used for a variety of cancers, including colorectal, lung, glioblastoma, breast, liver, and kidney cancer.

### What is single cell RNA-seq (scRNA-seq)?
Given a collection of cells, scRNA-seq is generally able to do the following for each cell: sequence each captured transcript (mRNA) from the cell's transcriptome and associate those sequenced transcripts with that cell (Jovic et al. 2022). Some example applications of scRNA-seq include: understanding the diversity of gene expression cells within a sample/environment (sample heterogeneity), determining how cell behavior varies spatio-temporally (for example, different parts of a tumor responding to oxygen access or drug exposure), comparing expression patterns of cell types (for example, compare immune vs blood vs neuron), discovering rare individual cells in a population (for example, hyper-resistant cancer cells), and tracing lineages of cells (tracking line of parental cells to progenitor cell(s)) (Haque et al. 2017).


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
3. Some stop/affect some key function supporting the cancer cell growth. 4. Some antibody therapies fit more than one of these mechanisms of action.

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

### Remaining Questions
- Where can we get "open source, scRNA-seq data collected from a variety of cancer cell lines"? CCLE?
- What kind of cancers should I expect to behave like the ones treated by Trastuzumab and Bevacizumab? Obvious starting point: find cancers with VEGF and/or HER2 over-expression; perhaps cancers that have similar causal mechanisms to HER2 and/or VEGF? 
- What kind of (statistical) analysis on the scRNA-seq data will help determine that Trastuzumab and/or Bevacizumab might on a given cancer cell line? One sanity check is to make sure that the analysis shows that the cancers *we know they **are** effective on* are confirmed by our analysis (and cancers that we know they are not effective on).

## References
Bevacizumab [Package Insert]. (2022, September 18). Genentech. https://www.accessdata.fda.gov/drugsatfda_docs/label/2022/125085s340lbl.pdf

Gerriets V, Kasi A. Bevacizumab. [Updated 2023 Aug 28]. In: StatPearls [Internet]. Treasure Island (FL): StatPearls Publishing; 2024 Jan-. Available from: https://www.ncbi.nlm.nih.gov/books/NBK482126/

Greenblatt K, Khaddour K. Trastuzumab. [Updated 2024 Jun 22]. In: StatPearls [Internet]. Treasure Island (FL): StatPearls Publishing; 2024 Jan-. Available from: https://www.ncbi.nlm.nih.gov/books/NBK532246/

Haque, A., Engel, J., Teichmann, S. A., & Lönnberg, T. (2017). A practical guide to single-cell RNA-sequencing for biomedical research and clinical applications. Genome medicine, 9, 1-12. https://doi.org/10.1186/s13073-017-0467-4

Herceptin [Package Insert]. (2024, June 18). Genentech. https://www.accessdata.fda.gov/drugsatfda_docs/label/2024/103792s5354lbl.pdf

Jovic, D., Liang, X., Zeng, H., Lin, L., Xu, F., & Luo, Y. (2022). Single‐cell RNA sequencing technologies and applications: A brief overview. Clinical and translational medicine, 12(3), e694. https://doi.org/10.1002/ctm2.694

Mirabelli, P., Coppola, L., & Salvatore, M. (2019). Cancer cell lines are useful model systems for medical research. Cancers, 11(8), 1098. https://doi.org/10.3390/cancers11081098

National Research Council (US) Committee on Methods of Producing Monoclonal Antibodies. Monoclonal Antibody Production. Washington (DC): National Academies Press (US); 1999. Introduction. Available from: https://www.ncbi.nlm.nih.gov/books/NBK100188/

Runcie, K., Budman, D. R., John, V., & Seetharamu, N. (2018). Bi-specific and tri-specific antibodies-the next big thing in solid tumor therapeutics. Molecular Medicine, 24, 1-15. https://doi.org/10.1186/s10020-018-0051-4

Shepard, H. M., Phillips, G. L., Thanos, C. D., & Feldmann, M. (2017). Developments in therapy with monoclonal antibodies and related proteins. Clinical medicine, 17(3), 220-232. https://doi.org/10.7861/clinmedicine.17-3-220

The Antibody Society. Therapeutic monoclonal antibodies approved or in review in the EU or US. (2024); https://www.antibodysociety.org/resources/approved-antibodies.

Wang, X. Z., Coljee, V. W., & Maynard, J. A. (2013). Back to the future: recombinant polyclonal antibody therapeutics. Current opinion in chemical engineering, 2(4), 405-415. https://doi.org/10.1016/j.coche.2013.08.005

# Miscellaneous Information

## The 5 types of human antibodies
See this [resource](https://ruo.mbl.co.jp/bio/e/support/method/antibody-isotype.html#:~:text=Human%20antibodies%20are%20classified%20into,with%20distinct%20characteristics%20and%20roles.&text=IgG%20is%20the%20most%20abundant,of%20human%20immunoglobulins%20(antibodies).)

## Official FDA approved labels resource
- https://labels.fda.gov/
- to access drug labels specifically: link above > "Drugs" Tab > "Drugs@FDA"
