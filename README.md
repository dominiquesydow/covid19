# COVID-19 main protease: Ligands from similar binding sites

Read across the PDB to find similar binding sites and their associated molecules.

## Steps

### Target and binding site definition

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
   
   Check out notebook [here](https://github.com/dominiquesydow/covid19/blob/master/notebooks/binding_site_definition.ipynb).

### Similar binding sites / proteins

4. [Done] Submit job to ProBis, including binding site definition
   - Full 6LU7: [ProBis job URL](http://probis.cmm.ki.si/?what=job&job_id=24032003478165)
   - Binding site only:  
   
     | # residues | distance cutoff | coverage cutoff | ProBis job URL                                                            |
     |------------|-----------------|-----------------|---------------------------------------------------------------------------|
     | 68         | 15              | 0.5             | [ProBis job URL](http://probis.cmm.ki.si/?what=job&job_id=25032048431709) |

5. [Done] Download ProBis results
   - *ProBis protein table*: "Similar Proteins" tab > "Download Table"
   - *ProBis ligand table*: "Predicted Ligands" tab > "Download Table"
   
   ProBis results live [here](https://github.com/dominiquesydow/covid19/tree/master/data/probis).
   
6. [Done] Parse ProBis ligand and protein tables

   Check out notebook [here](https://github.com/dominiquesydow/covid19/blob/master/notebooks/probis_data_preparation.ipynb).

### Active molecules against similar proteins

7. [Done] Query ChEMBL for "active" molecules, given a defined pIC50 cutoff (`chembl_webresource_client`)
   
   - Get molecule and bioactivity data for proteins from *ProBis protein table* (by UniProt IDs).
   - Filter ChEMBL molecules by bioactivity (define threshold) to keep only “active” molecules.

   Checkout notebooks:
   - Pipeline (to obtain molecule library) [here](https://github.com/dominiquesydow/covid19/blob/master/notebooks/chembl_molecules_from_uniprot_ids.ipynb).
   - Result (molecule library) [here](https://github.com/dominiquesydow/covid19/blob/master/notebooks/molecule_library.ipynb).
   
8. ProBis offers also prediced ligands (*ProBis ligand table*).
   - Find out how this dataset can be of use here.
   - Get molecule and bioactivity data for ligands from *ProBis ligand table* by ligand name?



