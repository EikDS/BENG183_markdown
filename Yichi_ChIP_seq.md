# ChIP-Sequencing

<p align="center">
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/Genome-wide-mapping-of-histone-modifications-and-other-DNAeprotein-interactions-has.png' alt='missing' height='300' />
    <figcaption> Chromatin immunoprecipitation (ChIP) is an important experimental technique for studying interactions between specific proteins and DNA in the cell and determining their localization on a specific genomic locus. In recent years, the combination of ChIP with second generation DNA-sequencing technology (ChIP-seq) allows precise genomic functional assay. </figcaption>
</p>

## Table of content
- [Biological Background](#biological-background)
    - [Chromatin Structure](#chromatin-structure)
    - [Immunoprecipitation](#immunoprecipitation)
    - [Sequencing](#sequencing)
- [Experimental Considerations](#experimental-considerations)
    - [Prepare Samples](#prepare-samples)
    - [Sequencing](#sequencing)
        - [Coverage and What Coverage Should be Used](#coverage-and-what-coverage-should-be-used)
        - [Library Preparation](#library-preparation)
- [Data Analysis](#data-analysis)
- [References](#references)

## Biological Background

The biological significance of protein interactions with DNA is critical for many vital cellular functions, such as DNA-replication, recombination, repair, gene expression, cell differentiation, cell cycle progression, chromosome stability, and epigenetic silencing etc. In eukaryotic cells, genetic elements are maintained in dynamic chromatin structures.

### Chromatin Structure

<p align="center">
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/Chromatin-structure-DNA-is-wrapped-around-a-histone-octamer-to-form-nucleosomes.png' alt='missing' />
    <figcaption>Chromatin structure. DNA is wrapped around a histone octamer to form nucleosomes. Nucleosomes are connected by stretches of linker DNA. This basic nucleosome structure is folded into a fiber-like structure of about 30 nm in diameter. These 30-nm fibers are further compacted into higher-order structures, which have not been characterized in detail. (Adapted from reference 45a with permission of Macmillan Publishers Ltd., copyright 2003.) </figcaption>
</p>

### Immunoprecipitation

Immunoprecipitation (IP) is the small-scale affinity purification of antigens using a specific antibody that is immobilized to a solid support such as magnetic particles or agarose resin. Immunoprecipitation is one of the most widely used methods for isolation of proteins and other biomolecules (in this case, chromatin DNA fragments) from cell or tissue lysates for the purpose of subsequent detection by western blotting and other assay techniques.

<p align="center">
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/immunoprecipitation.gif' alt='missing' />
    <figcaption>Each step involves incubation, followed by bead collection (centrifugation or magnetic) and removal of the solution. Wash steps are also included after each incubation step. Elution during the final step typically involves heating the beads in sample loading buffer for polyacrylamide gel electrophoresis (SDS-PAGE), which results in denaturation of the proteins (including the antibody) and irreparable damage to the beads, which are discarded. (Adapted from https://www.leinco.com/immunoprecipitation-protocol) </figcaption>
</p>

### Sequencing

The current sequencing technologies are based on [Sanger Sequencing](https://en.wikipedia.org/wiki/Sanger_sequencing), but with an much higher efficiency. The next generation sequencings allow for massively parallel sequencing reactions. These systems are capable of analyzing millions or even billions of sequencing reactions at the same time. Although different machines have been developed with various differing technical details, they all share some common features which are outlined below.

#### 1. Sample Preparation:
All Next Generation Sequencing platforms require a library obtained either by amplification or ligation with custom adapter sequences. These adapter sequences allow for library hybridization to the sequencing chips and provide a universal priming site for sequencing primers.

#### 2. Sequencing machines:

Each library fragment is amplified on a solid surface (either beads or a flat silicon derived surface) with covalently attached DNA linkers that hybridize the library adapters. This amplification creates clusters of DNA, each originating from a single library fragment; each cluster will act as an individual sequencing reaction.
The sequence of each cluster is optically read (either through the generation of light or fluorescent signal) from repeated cycles of nucleotide incorporation. Each machine has its own unique cycling condition.

#### 3. Data output:
Each machine provides the raw data at the end of the sequencing run. This raw data is a collection of DNA sequences that were generated at each cluster. This data could be further analysed to provide more meaningful results.

An illustration of the similarities and difference between the different Next Generation Sequencing platforms adapted from [abmgood](https://www.abmgood.com/marketing/knowledge_base/next_generation_sequencing_introduction.php)
<p align="center">
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/Next_Generation_Sequencing_NGS_Comparisons_of_Sequencing_By_Ligation_Sequencing_By_Synthesis_Pyrosequencing.png' alt='missing' />
    <figcaption> </figcaption>
</p>

## Experimental Considerations

### Prepare Samples
Harvesting cells. There is a noticeable increase in the size of the cell pellet in time courses lasting 4 hr or longer. To compensate for this, smaller samples are taken at later time points and diluted with YEP-lactate to bring the volume up to 45 ml, based on OD600 measurements.

Optimizing ChIP. There are several variables in the ChIP protocol that may be optimized including the degree of crosslinking, cell lysis and sonication of DNA. The degree of crosslinking can be varied by changing the incubation time with formaldehyde. Cell lysis should also be optimized since it is dependent on the vortexer. Intact cells can be counted under a microscope using a hemacytometer. Sonication conditions also should be adjusted such that the DNA size average is about 150
bp since we want DNAs from every chomatin. The quality and effectiveness of the antibody should also be checked by
examining the Non-IP and Post-IP samples on Western blots. The optimal antibody dosage should also be determined.

### Sequencing
#### Coverage and What Coverage Should be Used
The current NGS platforms available on the market, although very accurate, are still prone to error. Even at accuracies of 99% and greater, a sequence generated may contain incorrect nucleotides. This means that if a machine’s accuracy is 99%, one base pair is read incorrectly out of 100 base pairs; since NGS platforms generate high amounts of output, these errors can add up quickly. The way to circumvent NGS platform limitations is to sequence nucleotides multiple times. The number of times a nucleotide is sequenced is referred to as “coverage”, or “depth”. Coverage may also be used to refer to the percentage of target bases that have been sequenced a specific number of times.

Coverage will vary depending on the type of NGS and the research application. More coverage tends to be used when in search for a variant that is less common (<1%) in a sample. An example is the detection of cancer mutations in tumour DNA circulating in the plasma of cancer patients. However, the appropriate coverage for an experiment is determined on a case-by-case basis. The coverage also varies depending on the NGS type (i.e. Whole Genome Sequencing). For instance, whole genome sequencing generally requires approximately 30x coverage, as this will detect 98% of heterozygous single nucleotide variants identified in a microarray. There is a way to compute coverage, as shown in the Lander-Waterman equation below.
<p align="center">
    C = LN/G

    C = coverage
    G = haploid genome length (in nucleotides)
    L = read length (in nucleotides)
    N = number of reads

More information about coverage choosing can be found on [genohub](https://genohub.com/recommended-sequencing-coverage-by-application/)

#### Library Preparation
Before a sample can be sequenced, it must be prepared into a sample library from genomic DNA or total RNA. A library is a collection of randomly sized DNA fragments that represent the sample input. However, depending on the type of applications, different library preparation steps are taken. Prior to sequencing, the sample library must be validated quantitatively and qualitatively. This is performed to verify if there is a sufficient amount of good quality DNA in the prepared library. Both quality and quantity play important roles in generating data. The consequence of having either more or less DNA than the optimal amount set by the library protocol is that the sequencing reaction runs less efficiently. This generates low quality data through problems including read problems from flow cell saturation, or reduced coverage because of insufficient DNA. In terms of quality, a good quality library is one that has a diverse set of DNA fragments with minimal duplicate fragments. This is important because during PCR amplification of some sample library preparation protocols, duplicates of fragments will be generated. The consequence of duplicate fragments is that the sequencing reaction will be biased towards these fragments.

qPCR is a method of quantifying a sample library before sequencing. It is ideal when there is an insufficient amount available for fluorometric quantification, commonly due to no PCR amplification. It is also a more sensitive way, relative to Qubit, to quantify the adapter-ligated fragments in a sample. qPCR selectively amplifies such fragments, so it avoids the inaccuracies of Qubit that result from being unable to distinguish between fragments which can and cannot be sequenced. The only drawback to this procedure is that it is very time-consuming.

Qubit is an alternative to qPCR for quantifying a sample library. Relative to qPCR, it provides results faster; however, it is not applicable for cases where there is no PCR enrichment as it is less sensitive than qPCR and requires more sample. Quantification is performed by illuminating and detecting dyes which selectively bind to DNA or RNA. First, a standard must be measured with the appropriate assay. The sample, which may be diluted, is then mixed with the appropriate dye before being inserted into the machine.

## Data Analysis
<p align="center">
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/Screenshot%20from%202018-12-13%2023-29-18.png' alt='missing' />
    <figcaption>An example of treating sequencing data, provided by Endre Barta, University of Debrecen, Center for Clinic Genomics</figcaption>
</p>
1. Processing raw-sequencing data: Check the overall quality of the reads, sequence composition, GC bias, adaptor pollution, quality and adaptor trimming.
<p align="center">
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/Screenshot%20from%202018-12-14%2000-05-55.png' alt='missing' />
    <figcaption></figcaption>
</p>

2. Align reads to the referene genome: using aligner programs and SAM file as input.

3. visualization of the genomic data: A recommanded tool is [GIVE](https://www.givengine.org/data-hub.html).

4. Find peaks. Many types of experiments also seek to identify locations in which sequence reads cluster into ‘regions of enrichment’, in which overlapping reads appear as peaks. For ChIP-Seq experiments, such areas represent in vivo locations where proteins of interest (e.g. modified histones or transcription factors) were associated with DNA; for transcriptome experiments, they correspond to the locations of transcribed exons.

Previously, enriched regions in ChIP-Seq experiments have been identified by enumerating genome-wide profiles of extended virtual fragments based upon the aligned position of the short sequencing reads. Several unpublished software packages are available for this goal (‘Minimal ChipSeq Peak Finder’, Wold lab, Caltech, ‘Chip-Seq Data Analysis’, Illumina Inc.).
<p>
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/Screenshot%20from%202018-12-14%2000-18-21.png' height=400 alt='missing' />
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/Screenshot%20from%202018-12-14%2000-18-06.png' height=400 alt='missing' align="right" />
    <figcaption>Provided by Endre Barta, University of Debrecen, Center for Clinic Genomics</figcaption>
</p>

## References
1. Sequencing depth and coverage: key considerations in genomic analyses. Sims, D., et al. 2, 2014, Nature Reviews Genetics, Vol. 15, pp. 121-132.

2. Noninvasive identification and monitoring of cancer mutations by targeted deep sequencing of plasma DNA. Forshew, T., et al. 136, 2012, Cancer Genomics, Vol. 4.

3. Library construction for next-generation sequencing: Overviews and challenges. Head, S.R., et al. 2, 2014, BioTechniques, Vol. 56, pp. 61-77.

4. Immunoprecipitation Protocol. https://www.leinco.com/immunoprecipitation-protocol

5. Overview of the Immunoprecipitation (IP) Technique. https://www.thermofisher.com/us/en/home/life-science/protein-biology/protein-biology-learning-center/protein-biology-resource-library/pierce-protein-methods/immunoprecipitation-ip.html

6. Anthony P. Fejes, Gordon Robertson, Mikhail Bilenky, Richard Varhol, Matthew Bainbridge, Steven J. M. Jones; FindPeaks 3.1: a tool for identifying areas of enrichment from massively parallel short-read sequencing technology , Bioinformatics, Volume 24, Issue 15, 1 August 2008, Pages 1729–1730

7.  Rasika Mundade, Hatice Gulcin Ozer, Han Wei, Lakshmi Prabhu & Tao Lu (2014) Role of ChIP-seq in the discovery of transcription factor binding sites, differential gene regulation mechanism, epigenetic marks and beyond, Cell Cycle, 13:18, 2847-2852, DOI: 10.4161/15384101.2014.949201 

8. Ryuichiro Nakato, Katsuhiko Shirahige; Recent advances in ChIP-seq analysis: from quality management to whole-genome annotation, Briefings in Bioinformatics, Volume 18, Issue 2, 1 March 2017, Pages 279–290

9. ChIP–seq and beyond: new and improved methodologies to detect and characterize protein–DNA interactions,Terrence S. Furey, Nature Reviews Genetics volume 13, pages 840–852 (2012)

10. ChIP-Seq: technical considerations for obtaining high-quality data, Benjamin L Kidder, Gangqing Hu & Keji Zhao, Nature Immunology volume 12, pages 918–922 (2011)
