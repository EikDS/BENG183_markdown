# ChIP-Sequencing

<figure>
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/Genome-wide-mapping-of-histone-modifications-and-other-DNAeprotein-interactions-has.png' alt='missing' height='300' />
    <figcaption> Chromatin immunoprecipitation (ChIP) is an important experimental technique for studying interactions between specific proteins and DNA in the cell and determining their localization on a specific genomic locus. In recent years, the combination of ChIP with second generation DNA-sequencing technology (ChIP-seq) allows precise genomic functional assay. </figcaption>
</figure>

## Table of content
- [Biological Background](#bio_background)
    - [Chromatin Structure](#chromatin)
    - [Immunoprecipitation](#immunoprecipitation)
    - [Sequencing](#sequencing)
- [Experimental Considerations](#experiment)
    - [Prepare Samples](#sample)
    - [Prepare Sequencing](#sequencing)
- [Data Analysis](#data)
    - [Normalization](#normalization)
    - [Mapping](#mapping)
- [Referenes](#referenes)

## Biological Background

The biological significance of protein interactions with DNA is critical for many vital cellular functions, such as DNA-replication, recombination, repair, gene expression, cell differentiation, cell cycle progression, chromosome stability, and epigenetic silencing etc. In eukaryotic cells, genetic elements are maintained in dynamic chromatin structures.

### Chromatin Structure

<figure>
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/Chromatin-structure-DNA-is-wrapped-around-a-histone-octamer-to-form-nucleosomes.png' alt='missing' />
    <figcaption>Chromatin structure. DNA is wrapped around a histone octamer to form nucleosomes. Nucleosomes are connected by stretches of linker DNA. This basic nucleosome structure is folded into a fiber-like structure of about 30 nm in diameter. These 30-nm fibers are further compacted into higher-order structures, which have not been characterized in detail. (Adapted from reference 45a with permission of Macmillan Publishers Ltd., copyright 2003.) </figcaption>
</figure>

### Immunoprecipitation

Immunoprecipitation (IP) is the small-scale affinity purification of antigens using a specific antibody that is immobilized to a solid support such as magnetic particles or agarose resin. Immunoprecipitation is one of the most widely used methods for isolation of proteins and other biomolecules (in this case, chromatin DNA fragments) from cell or tissue lysates for the purpose of subsequent detection by western blotting and other assay techniques.

<figure>
    <img src='https://github.com/EikDS/BENG183_markdown/blob/master/immunoprecipitation.gif' alt='missing' />
    <figcaption>Each step involves incubation, followed by bead collection (centrifugation or magnetic) and removal of the solution. Wash steps are also included after each incubation step. Elution during the final step typically involves heating the beads in sample loading buffer for polyacrylamide gel electrophoresis (SDS-PAGE), which results in denaturation of the proteins (including the antibody) and irreparable damage to the beads, which are discarded. (Adapted from https://www.leinco.com/immunoprecipitation-protocol) </figcaption>
</figure>

### Sequencing

The current sequencing technologies are based on [Sanger Sequencing](https://en.wikipedia.org/wiki/Sanger_sequencing), but with an much higher efficiency. The next generation sequencings allow for massively parallel sequencing reactions. These systems are capable of analyzing millions or even billions of sequencing reactions at the same time. Although different machines have been developed with various differing technical details, they all share some common features which are outlined below.
