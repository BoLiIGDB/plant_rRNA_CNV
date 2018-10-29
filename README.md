# plant_rRNA_CNV
A pipeline to call copy number of repeat elements, e.g. rRNA 
To accurate estimate the copy number of tandem repeat elements in one individual genome with resequencing data, you firstly need to know your target repeats, which should be nearly identical with each other, such as 45S rRNA gene or 5S rRNA gene. However, tRNA, miRNA even centromere repeats are not best candidate to be calculated by using this method.

To run this pipeline, you needs the following input files:
1. reference genome: sequence (in FASTA format) and annotation (GFF3 format)
2. resequencing data: clean FASTQ data (e.g. Illumina)

To run this pipeline, you need the following tools pre-installed in your computer:
1. bwa or bowtie
2. SAMtools and BEDtools
3. BLAST
4. R

This pipeline includes 3 main steps:

1. Identify single copy genomic regions, which can be used as overall background read depth;
2. mapping short reads onto genome, and calculate read depth for both target repeats and single copy region;
3. take the ratio between read depth of repeat and single copy, and finally get the estimated copy number.
