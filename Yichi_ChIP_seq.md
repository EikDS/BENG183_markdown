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
    - [Prepare Sequencing](#prepare-sequencing)
- [Data Analysis](#data-analysis)
    - [Normalization](#normalization)
    - [Mapping](#mapping)
- [Referenes](#referenes)

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

