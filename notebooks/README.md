# Notebooks

Read across the PDB to find similar binding sites and their associated molecules.


## Pipeline

1. Binding site definition
   - Define target's binding site based on multiple ligand positions.
   - Notebook: [`binding_site_definition.ipynb`](https://github.com/dominiquesydow/covid19/blob/master/notebooks/binding_site_definition.ipynb)
2. Binding site comparison
   - Download results from ProBis (manually) and parse files
   - Get UniProt IDs from most similar proteins
   - Notebook: [`probis_data_preparation.ipynb`](https://github.com/dominiquesydow/covid19/blob/master/notebooks/probis_data_preparation.ipynb)
3. Molecules active against similar proteins
   - Get active molecules against similar proteins based on UniProt IDs (ChEMBL query)
   - Notebook: [`chembl_ligands_from_probis.ipynb`](https://github.com/dominiquesydow/covid19/blob/master/notebooks/chembl_molecules_from_uniprot_ids.ipynb)
4. Explore molecule library
   - Look at output molecule library
   - Notebook: [`molecule_library.ipynb`](https://github.com/dominiquesydow/covid19/blob/master/notebooks/molecule_library.ipynb)
   
Note: This pipeline could be automatized before (1.) and after (2.-4.) the manual ProBis step.
   
## Data

Pipeline at the example of:

- Pocket comparison only (15 A radius around ligand with 50% coverage across structures)
- [Data](https://github.com/dominiquesydow/covid19/tree/master/data/probis/probis_pocket_15_0.5)
- [ProBis job URL](http://probis.cmm.ki.si/?what=job&job_id=25032048431709)