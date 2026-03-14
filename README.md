# Drug-Name-to-SMILES-SwissADME-Batch-Generator
Python tool that converts drug names into canonical SMILES using the PubChem database and automatically generates batch files formatted for SwissADME analysis.
# Drug-Name-to-SMILES-SwissADME-Batch-Generator

A Python automation script that converts drug names into canonical SMILES strings using the PubChem database and generates SwissADME-ready batch input files.

This tool is useful for computational biology, cheminformatics, drug discovery, and ADME property prediction workflows where large numbers of drug names must be converted into SMILES format before submitting them to SwissADME.

---

## Overview

SwissADME requires compound input in the format:

SMILES DrugName

Manually converting hundreds of drug names to SMILES is time-consuming. This script automates the entire process by:

1. Reading drug names from a CSV file.
2. Querying the PubChem database.
3. Retrieving canonical SMILES structures.
4. Formatting the results for SwissADME.
5. Splitting compounds into batches of 100.
6. Exporting batch files ready for SwissADME submission.

---

## Features

Automatic conversion of drug names to canonical SMILES

Direct querying of the PubChem database using PubChemPy

Automatic formatting for SwissADME input requirements

Batch file generation (100 molecules per file)

Handles large drug lists efficiently

Reports compounds that could not be retrieved

Compatible with Google Colab, Jupyter Notebook, and local Python environments

---

## Requirements

Python 3.7+

Required Python libraries:

pandas
pubchempy

Install dependencies using pip:

pip install pandas pubchempy

---

## Input File

The script expects a CSV file containing drug names.

Example file:

Removed duplicates ANOVA.csv

The script automatically reads the first column and extracts unique drug names.

Example input format:

DrugName
Gefitinib
Cisplatin
Methotrexate
Docetaxel

---

## How the Script Works

Step 1
Load the CSV file containing drug names.

Step 2
Extract unique drug names.

Step 3
Query the PubChem database for each drug using PubChemPy.

Step 4
Retrieve the canonical SMILES string.

Step 5
Format each compound as:

SMILES DrugName

Step 6
Split the results into batches of 100 compounds.

Step 7
Save batch files for SwissADME submission.

---

## Output Files

The script generates batch files formatted for SwissADME.

Example output files:

SwissADME_Batch_1.txt
SwissADME_Batch_2.txt
SwissADME_Batch_3.txt

Example content inside the file:

COC1=C(C=C2C(=C1)N=CN=C2NC3=CC(=C(C=C3)F)Cl)OCCCN4CCOCC4 Gefitinib
N.N.Cl[Pt]Cl Cisplatin
CN(CC1=CN=C2C(=N1)C(=NC(=N2)N)N)C3=CC=C(C=C3)C(=O)NC Methotrexate

These files can be directly pasted or uploaded to the SwissADME web server.

---

## Usage

Run the script in Python or Jupyter Notebook.

Example:

python smiles_conversion.py

Or run the notebook in Google Colab.

Once completed, the script will generate SwissADME batch files in the working directory.

---

## Example Workflow

Drug list CSV
↓
PubChem query
↓
SMILES retrieval
↓
SwissADME formatting
↓
Batch file generation
↓
SwissADME analysis

---

## Applications

Drug discovery pipelines

ADME property prediction

Cheminformatics data preparation

High-throughput screening workflows

Computational pharmacology research

---

## Error Handling

If a drug name cannot be found in PubChem, the script records it in a failed drug list and continues processing the remaining compounds.

This ensures the pipeline runs without interruption.

---

## Future Improvements

Support additional chemical databases (ChEMBL, DrugBank)

Automatic SwissADME submission integration

Parallel processing for faster compound retrieval

Export formats for docking software and molecular modeling tools

---

## Author

Developed for computational biology and drug discovery workflows.

---

## License

This project is open source and available under the MIT License.
