When using these files please cite:
  F. M. Sousa, L. M. P. Lima, C. Arnarez, M. M. Pereira, M. N. Melo
  Coarse-grained parameterization of nucleotide cofactors and metabolites:
  protonation constants, partition coefficients, and model topologies.
  Journal of Chemical Information and Modeling, 2021, 10.1021/acs.jcim.0c01077

Mapping files in the 'mappings' subdir are provided for use with the backward
script. (http://www.cgmartini.nl/index.php/downloads/tools/240-backward)
They contain the CG mapping of representative cofactors from structures in
either the GROMOS nomenclature or the PDB nomenclature. File names indicate the
Martini cofactor acronym, but their '[ molecule ]' directive indicates the name
in the respective nomenclature. PDB names and atom nomenclatures were taken
from http://ligand-expo.rcsb.org/index.html

The backward script only accepts atomistic nomenclatures from a small hardcoded
list. Because the PBC nomenclature is absent from that list, the PDB mapping
files refer to their atomistic topology as 'charmm'.

** To CG-map a cofactor: **
 - Unpack the backward files;
 - Place these .map files in the backward-v5/Mapping directory;
 - For a structure 'cofactor.pdb' in the PDB nomenclature run:
    backward-v5/backward.py -f cofactor.pdb -o cofactor.gro -from charmm -to martini
 - For a structure 'cofactor.pdb' in the GROMOS nomenclature run:
    backward-v5/backward.py -f cofactor.pdb -o cofactor.gro -from gromos -to martini

Limitations:
  When mapping from GROMOS, the backward script cannot guess the mass of some
atoms whose names do not start by their element's letter. In that case CG, bead
positions may be mapped off-center. A short energy minimization will bring
these beads to their equilibrium interparticle distances.
  If the precise mapped position is needed from a GROMOS source, an alternative
approach can be used, as was done in the paper above:
 - A GROMACS index file should be constructed from the mapping, with one group
   per CG bead, discriminating each atom mapped to that bead. As an example for
   ATP:

   #file 'ATP.map.ndx'
    [ ADN1 ]
     5 6 7 8 9 10
    [ ADN2 ]
     2 3 4
    [ ADN3 ]
     1 11 12
    [ RBS1 ]
     13 14 15 22
    [ RBS2 ]
     16 17 18 19 20 21
    [ PO4A ]
     23 24 25 26 27
    [ PO4B ]
     27 28 29 30 31
    [ PO4C ]
     31 32 33 34 35

 - The GROMACS tool gmx traj can then be used to convert a 'cofactor.pdb'
   structure to a correctly-centered CG configuration. (A compatible GROMACS
   run input file 'cofactor.tpr' will be needed):

   gmx traj -f cofactor.pdb -s cofactor.tpr -n ATP.map.ndx -com -ng 8 -oxt ATP.cg.gro

   where -ng 8 is the number of groups in the .ndx file. Beware that while the
   resulting .gro file wll have the correct mapped positions, its bead names
   will be wrong.


