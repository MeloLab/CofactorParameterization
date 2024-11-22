# Martini 3 coarse-grain parameters for nucleotide cofactors

This directory contains nucleotide parameters for the Martini 3 force-field. A
manuscript is in preparation, but part of the development has been described
in [R. Barriga's MSc. thesis](https://run.unl.pt/bitstream/10362/151163/1/Thesis_RodrigoBarrigaAlves%20-%20Final%20Version.pdf).

The parameters, in GROMACS format, are in `nucleotides.itp`.
They are currently considered v0.9 (practically final), pending
publication/review, and have undergone some changes from the ones in R.
Barriga's thesis, including the extension to new molecules.
You can find the parameters used in the thesis under the
[`M3_beta tag`](https://github.com/MeloLab/CofactorParameterization/tree/M3_beta).

## Included molecules

- Monophosphate
- Diphosphate
- Triphosphate
- Adenosine triphosphate (ATP)
- Adenosine diphosphate (ADP)
- Adenosine monophosphate (AMP)
- Adenosine
- Nicotinamide adenine dinucleotide, oxidized form (NAD+)
- Nicotinamide adenine dinucleotide, reduced form (NADH)
- Nicotinamide adenine dinucleotide phosphate, oxidized form (NADP+)
- Nicotinamide adenine dinucleotide phosphate, reduced form (NADPH)
- Nicotinamide mononucleotide, oxidized form (NMN)
- Nicotinamide mononucleotide, reduced form (NMNH)
- Nicotinamide riboside, oxidized form
- Nicotinamide riboside, reduced form
- Flavin adenine dinucleotide, oxidized form (FAD)
- Flavin adenine dinucleotide, semiquinone form (FADH)
- Flavin adenine dinucleotide, reduced form (FADH2)
- Flavin mononucleotide, oxidized form (FMN)
- Flavin mononucleotide, semiquinone form (FMNH)
- Flavin mononucleotide, reduced form (FMNH2)
- Riboflavin, oxidized form
- Riboflavin, semiquinone form
- Riboflavin, reduced form
- Thiamine pyrophosphate
- Thiamine monophosphate
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
