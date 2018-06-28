# Microhaplotype_processing
visualization and re-calling of microhaplotypes from unfiltered Microhaplot output

visualization and re-calling of microhaplotype genotypes output from microhaplot (https://github.com/ngthomas/microhaplot)

This set of R-scripts allows visualization and manipulation of SNP genotype data starting from a unfiltered microhaplotype file exported from Microhaplot.

1) import an "observed unfiltered haplotype" file containing the microhaplotype information. Prior to this step, the file can be filtered to remove loci with N's in them using scripts by Eric Anderson (see .....)
2) remove haplotypes with rank >2 and generate genotype dataframe of haplotypes with rank 1 and 2
3) remove "rejected" loci based on previous review in the Microhapot Shiny app (e.g., coverage <x%); optional.
4) Remove microhaplotype genotypes that contain N's, and convert NA for no reads to "0" reads. Convert genotypes with only one haplotype into homozygotes. Set minimum read depth (minDP) and re-call genotypes based on allelic ratio (default AR=0.3).
extract the relevant data from the vcf file, format into a tidy dataframe and parse data.
5) Optional: Transform data into matrix of samples by loci, 2 columns per locus; write to .csv for analysis or data checking.
6) Optional: Generate similar matrix that also includes read counts for each allele. Write to .csv for data checking.
7) Generate plots of allele counts for each genotype, and at different scales for data checking. Output = pdf of 3 plots per locus, with guide lines for allelic ratios of 0.3 and 0.4 to check how well genotypes fit different calling schemes (e.g., minimum depth, allelic ratio) 9-10) 
8) Modify genotypes based on applying new minimum depth (minDP), allelic ratios, and excluded loci. (based on .csv file of parameters for each locus). 
9) Re-plot data as in 7 to visualize changes and repeat until acceptable.
10) (not implemented yet) remove or re-call individual genotypes (needs work; very labor intensive)
11) transform data for export as sample by locus matrix (ready for import by strataG for various population analyses), and re-plot final data set for records.
12) export data as one row per genotype (locus, position, sample_ID, genotype, allele1 depth, allele2 depth), for storage in database.
