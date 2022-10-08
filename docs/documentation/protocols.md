# Protocols

### 1) Structure retrieval
Crystallized structure (X-RAY diffraction structure) of the enzyme under consideration of this study was available on PDB or [Protein Data Bank](https://www.rcsb.org/). Structure of Laccase enzyme from the species Myceliophthora thermophilus was retrieved with PDB ID:[6F5K](https://www.rcsb.org/structure/6F5K) in the (.pdb) format.


### 2) Cleaning of files using PyMol 2.5
Laccase enzyme pdb file (PDB ID:6F5K) was cleaned up to prepare for molecular docking (rigid docking) using [PyMol 2.5](https://pymol.org/2/); all water molecules, ligands (which included copper ions, calcium ions, N-acetyl glucosamine, nonaethylene glycol and hydroxide ion) and hydrogen atoms were removed. Additionally 11 amino acids had to also be removed from the structure due to conformation errors caused by them in the AutoDock Vina program. 
Crystallized ligand of Nonaethylene Glycol (NE) was exported out to be docked for comparison purposes.

### 3) Ligand retrieval 
Ligands for the study Aflatoxin B1 [AFB1 - 186907](https://pubchem.ncbi.nlm.nih.gov/compound/186907) and Aflatoxin G1 [AFG1 - 14421](https://pubchem.ncbi.nlm.nih.gov/compound/14421)  were retrieved from [PubChem](https://pubchem.ncbi.nlm.nih.gov/) in SDF format.

### 4) Control molecular docking of cleaned up laccase with AFB1 and AFG1 using PyRx
Molecular docking was carried out using AutoDock Vina through [PyRx](https://pyrx.sourceforge.io/), the cleaned up laccase (.pdb file) was imported and converted into an AutoDock Macromolecule and the ligands and NE molecule were imported using OpenBabel. Their energies were minimized using the uff force field algorithm and were converted into pdbqt format for docking procedure. Blind docking was carried out due to lack of proper active site knowledge with maximized grid box feature.

### 5) Mutation predictions using HotSpot Wizard v3.1 
Cleaned up structure of laccase enzyme was uploaded to [HotSpot Wizard v3.1](https://loschmidt.chemi.muni.cz/hotspotwizard/) and the web-server was run and functional hotspots and stability hotspots were generated from the server. Best results were retrieved from the server. Residues besides recommended for mutation were also taken which were shown to be critical interacting residues in visualization of control clean laccase docking. 

### 6) Mutation predictions using [CUPSAT](http://cupsat.tu-bs.de/) server
It is well known that not only functional hotspot mutations but stability mutations improve catalytic efficiency. Cleaned up laccase PDB was uploaded to the server and the results csv file was retrieved with all the possible mutations. The data was sorted and only top 10 results were filtered out with highest values of Delta Delta G (DDG).

### 7) Mutagenesis of proteins using PyMol 
Cleaned up laccase PDB was loaded onto PyMol and through the [mutagenesis wizard](https://pymolwiki.org/index.php/Mutagenesis) each point mutation was introduced which was predicted by both servers and individual point mutation structures were exported out. 

### 8) Molecular Docking of mutants generated 
Each point mutated version of laccase was loaded onto PyRx and in the same process molecular docking was performed and results were filtered out to only include the best binding energies, with least RMSD/UB and RMSD/LB values. Best docked conformations were exported for visualization in PDB format from the PyRx console. 

### 9) Visualization using [BIOVIA Discovery Studio 2021](https://discover.3ds.com/discovery-studio-visualizer-download)
Control and each of the mutant proteins were loaded in discovery studio with their respective docked conformations and each of their Receptor-Ligand interactions were visualized in 2D and 3D to reveal interacting residues and types of interactions. 

### 10) Validation of best mutants and control docking through Molecular Dynamics using [Schrodinger Desmond](https://www.schrodinger.com/products/desmond)
The two base interaction complexes of cleaned_laccase with AFG1 and AFB1 and best two interacting mutants with their individual complexes were analyzed through Molecular Dynamics analysis using Desmond at 50ns after preparation of protein-ligand complexes using Protein Preparation Wizard. The system builder was utilized to also introduce counter salt ions of Sodium (Na) at 15mM concentration in the system. The dynamics simulation was run and reports were generated. 

### 11) Analysis of amino acid residues removed during cleaning of 6F5K laccase pdb using [MEGA-X](https://www.megasoftware.net/)
Mega-X alignment tool was used to align sequences of the base 6F5K laccase structure with the Cleaned_laccase_pdb generated using PyMol. 11 amino acid residues were removed. 
>The amino acids removed were as :-

>1. Position - 13, Amino acid removed - T
2. Position - 14, Amino acid removed - D
3. Position - 36, Amino acid removed - T
4. Position - 37, Amino acid removed - L
5. Position - 60, Amino acid removed - N
6. Position - 85, Amino acid removed - E
7. Position - 90, Amino acid removed - S
8. Position - 147, Amino acid removed - V
9. Position - 276, Amino acid removed - E
10. Position - 528, Amino acid removed - D
11. Position - 529, Amino acid removed - A

`All amino acids are represented by their single letter code`


