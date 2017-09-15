# Phylomerge
PhyloMerge is a program used to merge partial gene sequences if they belong to the same species. PhyloMerge can either pick one sequence (e.g. the longest) or it can merge monophyletic sequences into one longer sequence. It can also rearrange the gene tree on poorly supported bipartitions to group together sequences from some species of interest that may have been misplaced in the gene tree.

## Usage:
phylomerge input.sequence.file=XX.fasta input.method=tree input.tree.file=XX.tree choice.criterion=merge taxon.to.sequence=XX.reverselink  prescreening.on.size.by.taxon=no deletion.method=taxon selection.by.taxon=yes output.sequence.file=XX_Selected.fas rearrange.tree=y bootstrap.threshold=0.7

### NB: sequence and species names should not contain the character "%" used internally by the program.

## Options:
input.method=“tree” (could also be a distance matrix with the option “matrix")

deletion.method=“threshold" or “random” or “sample” or “taxon”. “threshold” removes sequences that are so close in the tree that their distance is lower than the “threshold” value (which is given as another option to the program, default is 0.01). “sample”: random choice of sample_size sequences (default is 10). “taxon”: choice is guided by the identity of the species the sequences come from. In cases several sequences from the same species are monophyletic, a choice will be made according to the “choice.criterion” option

choice.criterion=“length" or  “length.complete” or “merge”. “length” means the longest sequence is selected. “length.complete” : means the largest number of complete sites (no gaps). “merge” means that the set of monophyletic sequences is used to build one long “chimera” sequence corresponding to the merging of them.

selection.by.taxon=“no” or “yes"

sequence.to.taxon=linkfile : giving the link between gene names and taxon names. Can be replaced by the option taxon.to.sequence if you have the links the other way around.

species.to.remove= file containing set of species from which sequences should be removed

prescreening.on.size.by.taxon=“no" : removes the sequences that are very short compared to other sequences of the same species. If there is only one sequence in this species, it is not removed.

output.sequence.file=refined.fasta : output alignment refined by the software

rearrange.tree=y : rearranges the tree at bipartitions with low support to group together sequences from the same species

bootstrap.threshold=0.7 : threshold below which a bipartition may be rearranged

rename.sequences=false : if set to true, the program will rename the sequences by adding before the sequence names the species names (between the two, an "_" will be placed).

## Contact
Send me an email if you need more explanations: boussau@gmail.com
