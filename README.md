# AlphaFold2 IDR complex prediction

## *Overview*

...

## *Examples*

In every example folded protein domains are shown in surface representation and IDRs are shown in ribbon. AlphaFold predictions are shown in tan colour, while the experimentally determined structures are shown in purple (or similar) colours. In all cases below AlphaFold predicts the structure of folded domains near-perfectly (typically within 1-2A RMSD). These predicted structures are not shown separately as their surfaces coincides with the surface generated from the experimental structures.

**NRBOX motif in NRIP1 bound to ERR3**
*Definition:*
Short motif forming an amphipathic helix binding into a well defined, single hydrophobic pocket. Easy as it gets, AF works perfectly
1 ordered protein + 1 IDR
PDB:2gpo

*Results:*
RMSD between predicted and experimental ligand conformations: 0.718A
In the original structure only the core motif is visible, AlphaFold also predicts a helical structure for the flanking region. This is due to the fact that AlphaFold is required to assign coordinates for all input residues; however, is assigns a low pLDDT score to this region, correctly marking that it’s a low confidence structure prediction (and low pLDDT is a good predictor of disorder). On the motif region that is responsible for affinity/specificity, the AF model predicts even side chain conformations correctly.

<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/2gpo_structure_comparison.png" width="500" height="294">
<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/2gpo_lDDT.png" width="500" height="333">
