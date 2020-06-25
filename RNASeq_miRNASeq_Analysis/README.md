# Differential expression from both RNASeq and miRNASeq

**Goal:** determine differentially expressed genes between CM/controls, but more imporantly: between Controls, CM samples with TTN variants, and CM samples with no TTN variants. 
Essentially, trying to **stratify CM samples into two groups, with two potential mechanisms of action**: TTN+ and TTN-
In addition, integrating with miRNASeq data- potential biomarkers + DE gene/DE miRNA networks

**Steps:**
1. RNASeq DE (DESeq2 used throughout): comparing CM to controls. This analysis has been performed by many other groups, including here for comparison purposes.
2. RNASeq DE: TTN+ vs TTN- vs Controls
3. Overlap analysis of #2: how many DEGs are found in just TTN+? Just TTN-? Shared between the two?
4. Pathway analysis: do the TTN+/TTN- specific DEGs act through different pathways? How does this compare to the common CM pathways (from #1 DEGs)
5. miRNASeq DE: comparing CM to controls *Note: miRNA does not stratify based on TTN+/TTN-; there does not appear to be separate miRNA pathways for these two groups*
6. Integrating RNASeq DEGs with miRNASeq- overlaps, pathway analysis