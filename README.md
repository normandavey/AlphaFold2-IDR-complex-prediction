# AlphaFold2 IDR complex prediction

## *Overview*

...

## *Examples*

**NRBOX motif in NRIP1 bound to ERR3**
*Definition:*
Short motif forming an amphipathic helix binding into a well defined, single hydrophobic pocket. Easy as it gets, AF works perfectly
1 ordered protein + 1 IDR
PDB:2gpo

*Results:*
RMSD between predicted and experimental ligand conformations: 0.718A
In the original structure only the core motif is visible, AlphaFold also predicts a helical structure for the flanking region. This is due to the fact that AlphaFold is required to assign coordinates for all input residues; however, is assigns a low pLDDT score to this region, correctly marking that it’s a low confidence structure prediction (and low pLDDT is a good predictor of disorder). On the motif region that is responsible for affinity/specificity, the AF model predicts even side chain conformations correctly.


