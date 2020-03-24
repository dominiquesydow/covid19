# COVID-19 main protease: Ligands from similar binding sites

Read across the PDB to find similar binding sites and their associated ligands fro COVID-19 main protease.

## Potential steps

1. Decide on a target
  - COVID-19 main protease
2. Decide on PDB ID
  - 6LU7 (http://www.rcsb.org/structure/6LU7)
  - In complex with fragments from XChem fragment screen: https://www.diamond.ac.uk/covid-19/for-scientists/Main-protease-structure-and-XChem.html 
3. Define binding site residues
  - Load all XChem structures in Biopython
  - Get residues in 10 A (?) radius of ligand centroids
  - Find overlapping residues across all structures (define residue coverage threshold)
4. Submit job to ProBis, including binding site definition
5. Download ProBis results
  - Ligand table
  - Protein table
6. Process ligand table
  - Read in ligand names
  - Query ChEMBL by ligand names for ligands
7. Process protein table
  - Read in protein UniProt IDs
  - Query ChEMBL by UniProt IDs for associated ligands
8. Merge ChEMBL ligand data
  - Include SMILES, bioactivity data against measured targets
  - Define bioactivity threshold
  - Keep only “active” ligands (those measured against targets with threshold bioactivity)
9. Give ligand data to the next person in the COVID-19 pipeline

