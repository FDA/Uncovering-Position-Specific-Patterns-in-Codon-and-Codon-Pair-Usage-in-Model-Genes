# Background

This repository’s code and data accompany the manuscript, _Uncovering Position-Specific Patterns in Codon and Codon-Pair Usage in Model Genes._ Current strategies for optimizing gene therapeutics and recombinant protein production typically rely on universal host codon usage indices. However, it is becoming increasingly common to consider specific traits of the gene. In this study, we investigate position-specific variations in codon and adjacent codon-pair usage biases, offering potential for more tailored gene engineering approaches to optimize translational kinetics and the folding of encoded products.

We focus our analysis on the coding sequences of four coagulation factors: ADAMTS13, von Willebrand factor, Factor VIII, and Factor IX, which have been used in therapeutic applications. By aligning transcript homologs with human sequences for each gene using Discontiguous Megablast and MACSE, we assess “sequence-position-specific” codon and codon-pair usage biases. Species with homologs ranged from Primates and Artiodactyla (Even-toed Ungulates) to Testudines.

Position-specific positive codon-pair usage biases were observed that contrasted with codon-pair usage biases derived with conventional methods. Moreover, we observed that codon and codon-pair usages are highly associated at sequence positions despite little or no association in an alignment universally. Statistical significance of position-specific codon bias was quantified with permutation tests modified for codon alignments. The distinct biases observed at different positions in coding sequences highlight the importance of considering position-specific effects in codon optimization strategies.

# Dependencies

Download R’s dependencies using RStudio’s built in functionality or your preferred method from The Comprehensive R Archive Network (<https://cran.r-project.org/>), Bioconductor (<https://bioconductor.org/>), and/or GitHub (<https://github.com/>).

The primary input for this pipeline is a codon multiple sequence alignment. We provide a detailed procedure to generate a human anchored codon multiple sequence alignment with Discontiguous Megablast (<https://blast.ncbi.nlm.nih.gov/Blast.cgi>) and _Multiple Alignment of Coding Sequences Accounting for Frameshifts and Stop Codons_ ([MACSE – GE²pop (agap-ge2pop.org)](https://www.agap-ge2pop.org/macse/)) in our manuscript, but the pipeline is compatible with any codon multiple sequence alignment.

# Archived Datasets

Supplementary File 1.xlsx (Supplementary Table S1):

Information about human reference sequence and its homologs for four genes used in this study (Gene Accession Number, Protein Accession Number, Gene Symbol, Gene Description, Species, and Taxonomy Identifier). The entrez query used in each gene’s Discontiguous Megablast search is also reported.

Supplementary File 2, File 3, File 4, and File 5 (Supplementary Figures S1, S2, S3, S4): Human reference alignment’s visualization with NCBI’s Multiple sequence alignment viewer for _ADAMTS13, F8, F9, and VWF_, respectively. Sequence ID corresponds to Gene Accession Number and Start and End indicates the first and last nucleotide number of each sequence. Red lines indicate matching nucleotides, gray lines indicate unmatching nucleotides, and white lines indicate gaps.

- Supplementary File 2.svg is _ADAMTS13’_s plot.
- Supplementary File 3.svg is _Factor 8’s_ plot.
- Supplementary File 4.svg is _Factor 9’s_ plot.
- Supplementary File 5.svg is _Von Willebrand Factor’s_ plot.

Following the Multiple Sequence Alignment Viewer user guide, the human reference sequences were set as anchor sequences, because they were used for the Discontiguous Megablast Searches (NCBI 2023). An anchor sequence subsets an alignment to compare the anchor sequence with other sequences.

Supplementary File 6.xlsx (Supplementary Table S2):

Alignment- and Position-specific codon-pair usages and codon-pair usage bias parameters including RSCPF, CPS, and CPOE, for four human reference genes. Codon-pair position number starts with “codons 1 and 2” as “codon-pair position 1”. PTM: post translational modification. Amino acid pair conservation was estimated as the average score of adjacent conservation of amino acids by ConSurf. The “Synonymous?” column indicates how many codon(s) in the pair are synonymous to human the human codon-pair (0, 1, 2). CPS’s amino Nacid/amino acid pair term (Fmn/Fm·Fn) is reported for both alignment-specific and position-specific analyses. The “Optimal codon-pair” column describes each position-specific codon-pair with respect to the most observed amino acid pair (defined as optimal). A codon-pair was “position-specific” optimal if it has the highest observed RSCPF at that position. A codon-pair was “alignment-specific” optimal if it has the highest observed RSCPF in the alignment.

Supplementary File 7.xlsx (Supplementary Table S3):

Sequence- and Position-specific codon usage tables for four human reference genes.

Supplementary File 8.xlsx (Supplementary Table S4): 

Codon-pair symmetric uncertainty and amino acid pair symmetric uncertainty (transformed from corresponding codon-pair SU) by sequence position for the human reference alignments, sequence-specific random codon sampling, and position-specific random codon sampling. Primate/non-primate portion of the original alignment were also included. Amino acid pair conservation was estimated as the average score of adjacent conservation of amino acids by ConSurf. In “AAP SU cs CP SU” tab, the percent of positions whose codon-pair SU was less than, equal to, or greater than its amino acid pair SU for each gene’s original alignment were shown. Mean, median, and mode codon-pair/amino acid pair symmetric uncertainties are reported in the “SU summary statistics” tab for the human reference alignments, sequence-specific random codon sampling, and position-specific random codon sampling. Mean, median, and mode codon-pair/amino acid pair symmetric uncertainties calculated by domain are reported in the “CP SU and AAP conservation” tab for the human reference alignments. A table summarizing regression analyses between mean/median codon-pair symmetric uncertainty and amino acid pair conservation is also reported. Lastly, the tab, “Domain t-tests”, includes a table of domain vs. non-domain t-test results for all four genes. 

Supplementary File 9.pdf Legend (Supplementary Figure S5): 

Codon-pair symmetric uncertainty plots for each human reference gene. See the legend of Figure 3 for the definition of color keys for each information bar. Also shown are figures displaying the symmetric uncertainty for codon-pairs and amino acid pairs across the gene sequence. It compares SU values derived from the original human reference alignment(black) with those form target taxonomy group-only (yellow) and non-target group (green) subsets. 

Supplementary File 10.xlsx (Supplementary Table S5): 

Quantitative description of each human reference alignment position’s statistical significance of codon/codon-pair relationships. 96% and 100% quantiles of each position’s codon-pair SU distribution for each permutation type are computed with base R’s “quantile” function. Then, each human reference alignment position’s codon-pair SU was evaluated to see if it falls below, within, or above the permutation’s 96-100% codon-pair SU quantile range. Two-tailed p-values are also given for each comparison.

Supplementary File 11.xlsx (Supplementary Table S6):

Synonymous-weighted CPS, RSCPF, and CPOE by sequence position for the human reference alignments reported with the human amino acid pair, human codon-pair, amino acid pair conservation, domain, post-translational modifications, the human codon pair’s CPS, the human codon pair’s RSCPF, and the human codon pair’s CPOE. Amino acid pair conservation was estimated as the average score of adjacent conservation of amino acids by ConSurf. Mean and median synonymous-weighted CPS, RSCPF, and CPOE are reported in the “Synonymous-weighted CPBM Summary” tab. A table summarizing regression analyses between mean/median amino acid pair conservation and synonymous-weighted CPS/RSCPF/CPOE (respectively) is also reported in the “AAP Cons. and CPBM regression” tab.

Supplementary File 12.pdf (Supplementary Figure S6):

Examples of position-specific codon-pair usage bias in the top three quartiles of each human reference
gene. To highlight potential position-specific optimization candidates, open triangles and closed squares
were colored red if they were the most biased codon-pair synonymous with human. See the legend of
Figure 3 for the definition of color keys for each information bar.

Supplementary File 13.xlsx (Supplementary Table S7):

Summary of codon-pair biases of the codon-pairs shown in Supplementary File 12. Three categories, “Codon-pair preferred”, “Most preferred codon-pair was not observed at this position”, and “Other codon-pair preferred” are mutually exclusive.

Supplementary File 14.xlsx (Supplementary Table S8):

Table of codon-pair biases of experimentally validated single synonymous mutations that affect phenotype.

# Archived Scripts

The scripts are listed by the order they should be ran. Some of the scripts are computationally intensive and will have the best performance on a high-performance computing (HPC) platform. Computationally intensive scripts have “HPC” in their names, and the rest of the scripts have “Local” in their names.

- Local – transcript selection per species.R

This script extracts a single transcript per species from Discontiguous Megablast results (fasta, hit-table, descriptions, and GenBank).

- Local - Codon-alignment-validation.R

This script compares the codon usage of sequences from a codon alignment to their original sequences.

- HPC - Permuted_alignment_generator.R

This script generates random alignments using the positional and sequential random codon sampling methods from an input codon alignment.

- HPC - Permutation codon-pair SU.R

This script calculates the codon pair symmetric uncertainty test statistic for each random and original alignment.

- Local - SU test statistic plots.R

This script calculates the codon pair symmetric uncertainty test statistic for the input alignment.

- Local - SU functions.R

Helper functions for Local - SU test statistic plots.R and Local – Codon-pair bias metric figures.R.

- Local – Alignment-specific CPOE.R

This script calculates alignment-specific codon-pair observed to expected ratios (CPOE) for an input alignment.

- Local – Alignment-specific RSCPF and CPS.R

This script calculates alignment-specific relative synonymous codon-pair frequency (RSCPF) and codon-pair score (CPS) for an input alignment.

- Local – Position-specific RSCPF-CPS-CPOE.R

This script calculates position-specific relative synonymous codon-pair frequency (RSCPF), codon-pair score (CPS), and codon-pair observed to expected ratio (CPOE) for an input alignment.

- Local – Codon-pair bias metric figures.R

This script creates the figures from the manuscript for an input alignment.

- Local – analysis of position-specific optimal codon-pairs.R

This script performs the naïve codon-pair optimization algorithm and analysis discussed in Table 5.

# Authors

Nathan J. Clement <sup>1,+</sup>, Nobuko Hamasaki-Katagiri <sup>1,+</sup>, Brian Lin <sup>1,+</sup>, Anton A. Komar <sup>2</sup>, Michael DiCuccio <sup>3</sup>, Haim Bar <sup>4</sup>, and Chava Kimchi-Sarfaty <sup>1, \*</sup>

# Affiliations

<sup>1</sup> Hemostasis Branch 1, Division of Hemostasis, Office of Plasma Protein Therapeutics, Office Therapeutic Products, Center for Biologics Evaluation and Research, Food and Drug Administration, Silver Spring, MD 20993, USA.

<sup>2</sup> Center for Gene Regulation in Health and Disease, Department of Biological, Geological and Environmental Sciences, Cleveland State University, Cleveland, OH 44115, USA.

<sup>3</sup> Rockville, MD 20853, USA.

<sup>4</sup> Department of Statistics, University of Connecticut, Storrs, CT 06269, USA.

<sup>+</sup> Equal contributor

<sup>\*</sup> Corresponding author

Please direct questions to Nathan Clement ([nathan.clement@fda.hhs.gov](mailto:nathan.clement@fda.hhs.gov)) and Chava Kimchi-Sarfaty ([chava.kimchi-sarfaty@fda.hhs.gov](mailto:chava.kimchi-sarfaty@fda.hhs.gov)).

# Open-Source Disclaimer

This open-source software has been released as-is without expectation of support or future releases.