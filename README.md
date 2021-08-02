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


**pKID binding to the KIX domain**
*Definition:*
The disordered KID region binds to the KIX domain upon phosphorylation. pKID binds to two distinct patches on KIX adopting helical bound structures. The interaction is phospho-depndent and KIX isn’t fully stable in the unbound form, so the prediction of the domain structure might be more challenging than usual.
Composition: 1 ordered protein + 1 IDR
PDB:1kdx

*Results:*
AlphaFold correctly folds the KIX domain and it also correctly folds KID into a helical structure that is very close to the actual bound structure. However, it places KID in a completely different surface on the KIX domain. In contrast to previous errors, here AlphaFold assigns a high confidence to the prediction.
Interestingly, the region occupied by KID in the AlphaFold model is a true binding site, the C-terminal part of the bound FOXO3 TAD region shows a high similarity to KID in the predicted model (PDB:2lqh) (similarly to the lysine N-methyltransferase 2A peptide (PDB:2agh) and p65 peptide (PDB:5u4k) bound structures).

<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/1kdx_structure_comparison.png" width="500" height="306">
<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/1kdx_lDDT.png" width="500" height="333">


**TAD of RelA bound to the TAZ domain of CREB-binding protein (CBP)**
*Definition:*
The disordered RelA binding region is significantly longer than previous examples. It wraps around the TAZ domain making contacts at 4 distinct patches, adopting mostly helical conformations at these 4 sites.
1 ordered protein + 1 IDR
PDB:2lww

*Results:*
AlphaFold correctly folds the TAZ domain of CBP, even though the native structure contains 3 Zn2+ ions, which AF cannot model. AlphaFold also correctly identifies the four binding surfaces and also folds RelA into helical conformations at these sites. However, in the predicted structure RelA is in the wrong orientation. In the figure below, the measured RelA (purple) wraps counterclockwise with both termini on the bottom. The predicted RelA wraps in the opposite direction, with both termini on the top. AlphaFold again assigns a high confidence score to the peptide prediction.

<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/2lww_structure_comparison.png" width="500" height="306">
<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/2lww_lDDT.png" width="500" height="333">


**Cyclin-A2 bound to Cdc20**
*Definition:*
The disordered tail of cyclin-A2 binds to the beta propeller domain of Cdc20 using three motifs binding to three separate pockets. The bound structure of the IDR is coil-like without any regular secondary structures and the linkers between the three motifs remain disordered even upon binding.
1 ordered protein + 1 IDR
PDB:6q6g

*Results:*
AlphaFold folds the domain near perfectly; however, it cannot fold the IDR on the surface of the domain. It does recognize a hydrophobic patch in the IDR (AALAVL) and it places close to the true binding pocket for this bit, however in the wrong conformation (alpha helix instead of a coil-like conformation). The rest of the IDR has no predicted contacts with the domain.

<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/6q6g_structure_comparison.png" width="500" height="297">
<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/6q6g_lDDT.png" width="500" height="333">


**Phactr1 bound to PP1**
*Definition:*
A disordered part of Phactr1 wraps around the PP1 domain establishing contacts at several points. The N-terminal region adopts a coil-like structure with two short bits in beta-augmentation. The C-terminal region adopts a largely helical conformation.
PDB:6zee

*Results:*
AlphaFold correctly folds the domain and it very precisely finds the correct position and orientation for the IDR (RMSD=0.903A). The high precision might have something to do with the IDR being asymmetric (helical on one end, beta on the other), adopting regular secondary structure and being fairly long.

<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/6zee_structure_comparison.png" width="500" height="297">
<img src="https://github.com/normandavey/AlphaFold2-IDR-complex-prediction/blob/main/6zee_lDDT.png" width="500" height="333">






