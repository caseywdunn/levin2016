# Brief Communication Arising


This document is the draft text for a "Brief Communication Arising" to Levin *et al.* 2016. The requirements of this format are described at the [Nature website]( http://www.nature.com/nature/authors/gta/commsarising.html). 


Please see the [git repository](https://github.com/caseywdunn/levin2016) for this manuscript for additional information. We welcome feedback, via the [issue tracker](https://github.com/caseywdunn/levin2016/issues), pull requests, or email.


-------------------------------------------------------------


## No support for inverse hourglass model


ARISING FROM: [Levin *et al. Nature* 531, 637-641 (2016)](http://dx.doi.org/10.1038/nature16994)


How changes in animal development relate to the evolution of animal diversity is a major question in evolutionary developmental biology (EvoDevo). To address this topic, Levin *et al.* <sup>1</sup> analyzed gene expression through the course of embryonic development for ten animal species, each from a different phylum. As their title ("The mid-developmental transition and the evolution of animal body plans") indicates, they arrived at two major conclusions. First, animal development is characterized by a well-defined mid-developmental transition. Second, this transition helps explain the evolution of features observed among distantly related animals. Specifically, they concluded that animals from different phyla exhibit an "inverse hourglass" model for the evolution of gene expression, where there is more evolutionary variance in gene expression at a mid phase of development than there is at early and late phases. Closely related animals have previously been described as having an hourglass model of gene expression, where evolutionary variance in expression is greater early and late in development than at the midpoint of development <sup>2,3</sup>. Levin *et al.* conclude that this contrast between distantly and closely related animals provides biological justification for the concept of phyla and may provide a long-sought operational definition of phyla. 


We previously described some concerns with their interpretations of these results <sup>4</sup>. Here we directly address problems with the analyses behind their evolutionary conclusions. Rather than support the inverse hourglass as a general pattern among distantly related species, our reanalyses of Levin *et al.* <sup>1</sup> support the opposite conclusion - that the inverse hourglass is due to large differences specific to a single lineage, the ctenophore (comb jelly). Better understanding these differences will be of interest to future work, especially in light of current uncertainty regarding the phylogenetic placement of ctenophores and their unique biology <sup>5,6</sup>. 


To understand our concerns with their analyses, it is helpful to first outline Levin *et al.*'s published methods and results. Although there are mature methods and tools for statistical analysis of character evolution <sup>7</sup> and gene expression <sup>8</sup>, Levin *et al.* <sup>1</sup> drew on neither of these very active areas of research and instead applied an *ad hoc* pairwise comparison of orthologous gene expression between species. They characterized each gene in each species as having expression that peaks in early, mid, or late temporal phase of development while the goodness of fit to these patterns was not considered, and alternative patterns were not evaluated. For each species pair, they then identified the orthologs shared by these species (shared orthologs vary from pair to pair). They then calculated a similarity score for each temporal phase for each species pair based on the fraction of genes that exhibited the same patterns in each species. The distributions of similarity scores are plotted in their [Figure 4d](http://www.nature.com/nature/journal/v531/n7596/fig_tab/nature16994_F4.html), and their Kolmogorov–Smirnov (KS) tests indicated that the early distribution and late distribution were each significantly different from mid distribution (P < 10<sup>-6</sup> and P < 10<sup>-12</sup>, respectively). This is the support they presented for the inverse hourglass model.


We began by examining the matrix of pairwise comparisons that their KS tests and Figure 4d are based on. As this figure shows (regenerated here as our Figure 1a), there is not a strong distinction between these temporal phases - the distributions for the early, mid, and late distributions overlap considerably. The medians are close in value, and the range of mid phase includes the entire range of the early phase. Further inspection (Figure 1a) reveals that the mid phase distribution has several outliers with very low similarity scores. We found that all five of the lowest values in the mid phase distribution are for pairwise comparisons that include the ctenophore (Figure 1a). When the nine pairwise comparisons that include the ctenophore are removed, the differences between the early and mid phase distributions are greatly reduced (Figure 1b).


We also found several problems with the statistical tests that were used to evaluate the inverse hourglass hypothesis. First, in the published analyses every data point was included twice because both reciprocal comparisons (which have the same values) were retained. For example, there is both a nematode to arthropod comparison and an arthropod to nematode comparison. As a consequence, there are 90 entries for the 45 pairwise comparisons, and by doubling the data the significance of the result appears much stronger than it actually is. After removing the duplicate values, the p values are far less significant, 0.002 for the early-mid comparison and on the order of 10<sup>-6</sup> for early-late. Second, the test they used (KS test) is not appropriate for the hypothesis they seek to evaluate. The KS test does not just evaluate whether one distribution is greater than the other, it also tests whether the shape of the distributions are the same. In addition, the samples in this dataset are matched (*i.e.*, for each pairwise comparison there is a early, mid, and late expression value), which the KS test does not take into account. The Wilcoxon test is instead appropriate in this case. After removing the duplicate scores, removing the ctenophore, and applying the Wilcoxon test, there is no significant difference between the early phase and mid phase distributions (P  = 0.1428 for the early-mid comparison and P < 10<sup>-5</sup> for the late-mid comparison), and in consequence the inverse hourglass turns into a wine bottle (Figure 1b). 


Our results highlight the importance of explicitly accounting for phylogenetic relationships when studying character evolution, including developmental <sup>9</sup> and functional genomic traits <sup>10</sup>. This is particularly true for evolutionary analyses of quantitative gene expression <sup>11</sup>. Pairwise comparisons result in the same evolutionary changes being counted multiple times in each species pair, as for the ctenophore comparisons that were mistaken for a global pattern here. This is a well understood property of pairwise comparisons that has been specifically addressed by phylogenetic comparative methods <sup>12</sup>. This particular case illustrates the shortcomings of *ad hoc* rank-based methods <sup>3</sup> and pairwise comparisons <sup>1</sup> for the study of the evolution of gene expression. Phylogenetic analyses of character evolution provide not only a way to avoid these problems, but a richer context for interpreting the biological implications of the results.


  

![Figure 1](./Figure1.png?raw=true)


> Figure 1 | Distributions of pairwise similarity scores for each phase of development. Pairwise scores for the ctenophore are red. Wilcoxon test p-values for the significance of the differences between early-mid distributions and late-mid distributions are on the right. Model of variance, which is inversely related to similarity, is on the left. (a) The distributions as published. Low similarity (*i.e.*, high variance) in the mid phase of development was interpreted as support for an inverse hourglass model for the evolution of gene expression. The five least-similar mid phase scores were all from the ctenophore. Published KS p-values, based on duplicated data, are in parentheses. The inset ctenophore image is by S. Haddock from phylopic.org. (b) The distributions after the exclusion of the ctenophore. The early and mid phase distributions are not statistically distinct. This suggest a wine bottle model, with similar evolutionary variance at the early and mid phase and less at the late phase.


### Methods
Levin *et al.* helpfully provided data and clarification on methods. We obtained the matrix of pairwise scores that underlies their [Figure 4d](http://www.nature.com/nature/journal/v531/n7596/fig_tab/nature16994_F4.html). We sorted this matrix by the mid-developmental transition column to see if any taxa were overrepresented among the low outliers, removed ctenophores, and applied the Wilcoxon test in place of the Kolmogorov-Smirnov test. These data, our analysis code, and additional information are available in a git repository at [https://github.com/caseywdunn/levin2016](https://github.com/caseywdunn/levin2016). The analysis workbook from this repository can be viewed at [https://rawgit.com/caseywdunn/levin2016/master/reanalyses.html](https://rawgit.com/caseywdunn/levin2016/master/reanalyses.html).


### References


1.	Levin, M. et al. The mid-developmental transition and the evolution of animal body plans. Nature 531, 637–641 (2016).
2.	Kalinka, A. T. et al. Gene expression divergence recapitulates the developmental hourglass model. Nature 468, 811–814 (2010).
3.	Domazet-Lošo, T. & Tautz, D. A phylogenetically based transcriptome age index mirrors ontogenetic divergence patterns. Nature 468, 815–818 (2010).
4.	Hejnol, A. & Dunn, C. W. Animal Evolution: Are Phyla Real? Curr. Biol. 26, R424–R426 (2016).
5.	Martindale, M. Q. & Henry, J. Q. Ctenophora In Evolutionary Developmental Biology of Invertebrates 1: Introduction, Non-Bilateria, Acoelomorpha, Xenoturbellida, Chaetognatha (Springer Vienna, 2015).
6.	Dunn, C. W., Leys, S. P. & Haddock, S. H. D. The hidden biology of sponges and ctenophores. Trends Ecol. Evol. 30, 282–291 (2015).
7.	Modern Phylogenetic Comparative Methods and Their Application in Evolutionary Biology. (Springer Berlin Heidelberg, 2014). doi:10.1007/978-3-662-43550-2
8.	Robinson, M. D., McCarthy, D. J. & Smyth, G. K. edgeR: a Bioconductor package for differential expression analysis of digital gene expression data. Bioinformatics 26, 139–140 (2009).
9.	Telford, M. J. & Budd, G. E. The place of phylogeny and cladistics in Evo-Devo research. Int. J. Dev. Biol. 47, 479–490 (2003).
10.	Hejnol, A. & Lowe, C. J. Embracing the comparative approach: how robust phylogenies and broader developmental sampling impacts the understanding of nervous system evolution. Philos. Trans. R. Soc. Lond., B, Biol. Sci. 370, 20150045–20150045 (2015).
11.	Dunn, C. W., Luo, X. & Wu, Z. Phylogenetic analysis of gene expression. Integr. Comp. Biol. 53, 847–856 (2013).
12.	Felsenstein, J. Phylogenies and the Comparative Method. American Naturalist 125, 1–15 (1985).


### Author information


#### Affiliations
Casey W. Dunn, Department of Ecology and Evolutionary Biology, Brown University, Providence, RI 02912, USA, casey_dunn@brown.edu


Andreas Hejnol, Sars International Centre for Marine Molecular Biology, University of Bergen, 5008 Bergen, Norway, andreas.hejnol@uib.no


#### Contributions
CWD performed the analyses. CWD and AH wrote the text.


#### Competing financial interests
Competing Financial Interests Declared none.


#### Corresponding author
Correspondence to: Casey W. Dunn, casey_dunn@brown.edu
