# Differential expression from both RNASeq and miRNASeq

## RNASeq Analysis approach:
**Goal:** determine differentially expressed genes between CM/controls, but more imporantly: between Controls, CM samples with TTN variants, and CM samples with no TTN variants. 
Essentially, trying to **stratify CM samples into two groups, with two potential mechanisms of action**: TTN+ and TTN-

Individual count matrices across 3 different sequence runs merged and preprocessed in `UKy_MergingRNACountsFilesAcross3Runs.Rmd`

**Steps:**
1. RNASeq DE (DESeq2 used throughout): comparing CM to controls. This analysis has been performed by many other groups, including here for comparison purposes. ***`RNASeq_DESeq2.Rmd`***
2. RNASeq DE: TTN+ vs TTN- vs Controls ***`RNASeq_DESeq2.Rmd`***
3. Overlap analysis of #2: how many DEGs are found in just TTN+? Just TTN-? Shared between the two? ***`RNASeq_DESeq2.Rmd`***
4. Pathway analysis: do the TTN+/TTN- specific DEGs act through different pathways? How does this compare to the common CM pathways (from #1 DEGs) ***`UKy_PathwayAnalysis.Rmd`***

**Graphical summary of approach (steps 2-4):**
![RNASeqApproach](RNASeq_DEMethod.PNG)

## miRNASeq Analysis approach:
**Goal:** Use DE analysis to identify potential biomarkers and integrate DE miRs with DEGs.

Two potential methods were used for generating miRNA count matrices:
1. BaseSpace app- produces both mature and isomiR counts. Files for individual samples combined in `miRNAPreprocessing_Combining_isomirSampleFiles_seqInfoIncluded_DownloadedSeparately_111419.Rmd`
2. Command line miRDeep2, using default settings (https://github.com/rajewsky-lab/mirdeep2). Produces only mature counts. This method chosen for downstream analysis.

**Steps:**
1. Perform DE analysis of miRNAs to identify DE miRs and potential miRNA biomarkers of DCM- `miRNA_DEAnalysis.Rmd`.
2. Identify miRNAs with high disease association by comparing differentially expressed miRNAs to their differentially expressed mRNA targets- `Integrating_RNASeq_and_miRNASeq_DE_Results.Rmd`. 
3. Determine what pathways the targets of this subset of miRNAs act in- `Integrating_RNASeq_and_miRNASeq_DE_Results.Rmd`


**Graphical summary of miRNA/mRNA integration approach:**

![miRNAApproach](miRNAMethod.PNG)
