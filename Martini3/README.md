# Martini 3 coarse-grain parameters for nucleotide cofactors

This directory contains nucleotide parameters for the Martini 3 force-field. A
manuscript is in preparation, but part of the development has been described
in [R. Barriga's MSc. thesis](https://run.unl.pt/bitstream/10362/151163/1/Thesis_RodrigoBarrigaAlves%20-%20Final%20Version.pdf).

The parameters, in GROMACS format, are in `nucleotides.itp`.
They are currently considered beta-version.

## Included molecules

- Monophosphate
- Diphosphate
- Triphosphate
- Adenosine
- Adenosine Triphosphate
- Adenosine Diphosphate
- Adenosine Monophosphate
- Nicotinamide Adenine Dinucleotide (ox)
- Nicotinamide Adenine Dinucleotide (r)
- Nicotinamide Riboside
- Nicotinamide Adenine Dinucleotide-phosphate (ox)
- Nicotinamide Adenine Dinucleotide-phosphate (r)
- Flavin Adenine Dinucleotide (ox)
- Flavin Adenine Dinucleotide (r)
- Flavin Mononucleotide (ox)
- Riboflavin (ox)
- Thiamine Pyrophosphate
- Thiamine Monophosphate
- Thiamine
- 2,5-Dimethyl-4-Aminopyrimidine

## Extra files
The mapping files from the reference GROMOS54A7 structures are included under
`mappings`. Only the main nucleotides ATP, NADPH, NADP+, NADH, NAD+, FAD and TPP
were parameterized from atomistic data; the remaining topologies were obtained
as fragments of those.

The CG structures were obtained by center-of-weights mapping the atomistic
coordinates of the atoms specified in the `.ndx` files into the respective
beads (weights indicated by the repetition of each atom).

The united-atom GROMOS structures had to be supplemented with explicit
hydrogens; one H-added atomistic structure per main nucleotide is included for
reference in `mappings` as well.
