# COVID-19 main protease: Ligands from similar binding sites

Read across the PDB to find similar binding sites and their associated ligands fro COVID-19 main protease.

## Potential steps

1. [Done] Decide on a target
   - COVID-19 main protease
2. [Done] Decide on PDB ID
   - [6LU7](http://www.rcsb.org/structure/6LU7)
   - In complex with fragments from [Diamond's XChem fragment screen](https://www.diamond.ac.uk/covid-19/for-scientists/Main-protease-structure-and-XChem.html) 
3. [Done] Define binding site residues
   - Load all XChem structures in Biopython
   - Get residues in a defined radius of ligand centroids
   - Find overlapping residues across all structures (define residue coverage threshold)
   - Check out [notebook](https://github.com/dominiquesydow/covid19/blob/master/notebooks/binding_site_definition.ipynb)
4. [Done] Submit job to ProBis, including binding site definition
   - Full 6LU7: [ProBis job URL](http://probis.cmm.ki.si/?what=job&job_id=24032003478165)
   - Binding site only:  
   
     | # residues | distance cutoff | coverage cutoff | ProBis job URL                                                            |
     |------------|-----------------|-----------------|---------------------------------------------------------------------------|
     | 68         | 15              | 0.5             | [ProBis job URL](http://probis.cmm.ki.si/?what=job&job_id=25032048431709) |

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

