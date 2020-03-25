# COVID-19 main protease: Ligands from similar binding sites

Read across the PDB to find similar binding sites and their associated ligands fro COVID-19 main protease.

## Potential steps

1. [Done] Decide on a target.
   - COVID-19 main protease
   
2. [Done] Decide on structure.
   - [6LU7](http://www.rcsb.org/structure/6LU7)
   - In complex with fragments from [Diamond's XChem fragment screen](https://www.diamond.ac.uk/covid-19/for-scientists/Main-protease-structure-and-XChem.html)
   
   Diamond's XChem fragment screen structures live [here](https://github.com/dominiquesydow/covid19/tree/master/data/Mpro_All_PDBs).

3. [Done] Define binding site residues.
   - Load all XChem structures in `biopython`.
   - Get residues in a defined radius of ligand centroids.
   - Find overlapping residues across all structures (define residue coverage threshold).
   - Check out [notebook](https://github.com/dominiquesydow/covid19/blob/master/notebooks/binding_site_definition.ipynb).

4. [Done] Submit job to ProBis, including binding site definition
   - Full 6LU7: [ProBis job URL](http://probis.cmm.ki.si/?what=job&job_id=24032003478165)
   - Binding site only:  
   
     | # residues | distance cutoff | coverage cutoff | ProBis job URL                                                            |
     |------------|-----------------|-----------------|---------------------------------------------------------------------------|
     | 68         | 15              | 0.5             | [ProBis job URL](http://probis.cmm.ki.si/?what=job&job_id=25032048431709) |

5. [Done] Download ProBis results
   - *ProBis ligand table*: "Predicted Ligands" tab > "Download Table"
   - *ProBis protein table*: "Similar Proteins" tab > "Download Table"
   
   ProBis results live [here](https://github.com/dominiquesydow/covid19/tree/master/data/probis)
   
6. [Done] Parse ProBis ligand and protein tables

   - Check out [notebook](https://github.com/dominiquesydow/covid19/blob/master/notebooks/probis_parser.ipynb).

7. Query ChEMBL for ligands (`chembl_webresource_client`)
   - Get ligand and bioactivity data for ligands from *ProBis ligand table* (by ligand name?).
   - Get ligand and bioactivity data for proteins from *ProBis protein table* (by UniProt IDs).
   - What kind of data should be saved?
     - Ligand data: SMILES, ...
     - Bioactivity data: Bioactivity against measured targets

8. Filter ChEMBL ligands by bioactivity (define threshold) to keep only “active” ligands.

9. Give ligand data to the next person in the COVID-19 pipeline.

