# AlphaFold2 IDR complex prediction

## *Overview*

...

## *Examples*

In every example folded protein domains are shown in surface representation and IDRs are shown in ribbon. AlphaFold predictions are shown in tan colour, while the experimentally determined structures are shown in purple (or similar) colours. In all cases below AlphaFold predicts the structure of folded domains near-perfectly (typically within 1-2A RMSD). These predicted structures are not shown separately as their surfaces coincides with the surface generated from the experimental structures.

**NRBOX motif in NRIP1 bound to ERR3**
*Definition:*
Short motif forming an amphipathic helix binding into a well defined, single hydrophobic pocket on the surface of the partner domain.
Composition: 1 ordered protein + 1 IDR
PDB:2gpo

*Results:*
RMSD between predicted and experimental ligand conformations: 0.718A
In the original structure only the core motif is visible, AlphaFold also predicts a helical structure for the flanking region. This is due to the fact that AlphaFold is required to assign coordinates for all input residues; however, is assigns a low pLDDT score to this region, correctly marking that it’s a low confidence structure prediction (and low pLDDT is a good predictor of disorder). On the motif region that is responsible for affinity/specificity, the AF model predicts even side chain conformations correctly.

<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/2gpo_structure_comparison.png" width="500" height="294">
<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/2gpo_lDDT.png" width="500" height="333">


**RanBP2 SIM (SUMO interacting motif) bound to SUMO**
*Definition:*
Short motif forming an additional strand in the beta sheet of the partner domain (beta augmentation).
Composition: 1 ordered protein + 1 IDR
PDB:2las

*Results:*
RMSD between predicted and experimental ligand conformations: 1.279A
AlphaFold correctly identifies the beta augmentation and the conformation of the side chains in the core motif. It does miss some stabilizing contacts at the edges, most notably it places the C-terminal Phe outside of the native binding pocket (flipping upwards in the top right of the image). AlphaFold correspondingly assigns a lower pLDDT value to the terminal regions of the peptide.

<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/2las_structure_comparison.png" width="500" height="306">
<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/2las_lDDT.png" width="500" height="333">


**Histone deacetylase 4 14-3-3 phosphomotif bound to 14-3-3gamma**
*Definition:*
A short IDR binding to a groove inside a 14-3-3 domain, adopting an irregular conformation. The interaction requires a phosphorylated serine.
Composition: 1 ordered protein + 1 IDR
PDB:3uzd

*Results:*
AlphaFold correctly identifies the binding groove and correctly assignes a coil-like conformation to the peptide, but is not able to fit the peptide into the correct position. One of the reasons could be that AlphaFold cannot model modified residues (the pSer in the original structure and the Ser in the predicted structure are shown in red).

<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/3uzd_structure_comparison.png" width="500" height="293">
<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/3uzd_lDDT.png" width="500" height="333">

 Using a phosphomimetic (modeling the interaction after switching the Ser to Glu in the peptide) improves the orientation a little but the pSer and Glu occupy very different positions and the confidence score does not improve, so it is likely due to random chance.

<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/3uzd_structure_comparison_mimE.png" width="500" height="293">
<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/3uzd_lDDT-mimE.png" width="500" height="333">

 
