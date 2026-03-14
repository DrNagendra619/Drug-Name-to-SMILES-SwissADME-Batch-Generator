# 🧪 Drug-Name-to-SMILES SwissADME Batch Generator

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![Cheminformatics](https://img.shields.io/badge/Field-Cheminformatics-green.svg)
![Automation](https://img.shields.io/badge/Workflow-Automation-orange.svg)
![Status](https://img.shields.io/badge/Status-Active-success.svg)
![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)

A **Python automation tool** that converts **drug names into canonical SMILES strings** using the **PubChem database** and automatically generates **batch input files formatted for SwissADME analysis**.

This tool is useful for **computational biology, cheminformatics, drug discovery, and ADME property prediction workflows**, where large numbers of drug names must be converted into SMILES format before submitting them to **SwissADME**.

---

# 📌 Overview

SwissADME requires compound input in the format:

```
SMILES DrugName
```

Manually converting hundreds of drug names to SMILES is **time-consuming and inefficient**.

This script **automates the entire workflow** by:

* Reading drug names from a CSV file
* Querying the PubChem database
* Retrieving canonical SMILES structures
* Formatting results for SwissADME
* Splitting compounds into batches of 100
* Exporting ready-to-use batch files

---

# ⚙️ Features

✅ Automatic conversion of **drug names → canonical SMILES**

✅ Direct querying of the **PubChem database using PubChemPy**

✅ Automatic formatting for **SwissADME input requirements**

✅ **Batch file generation (100 molecules per file)**

✅ Efficient handling of **large drug lists**

✅ Reports **compounds that could not be retrieved**

✅ Compatible with:

* Google Colab
* Jupyter Notebook
* Local Python environments

---

# 🧰 Requirements

### Python Version

```
Python 3.7+
```

### Required Python Libraries

* pandas
* pubchempy

### Install Dependencies

```
pip install pandas pubchempy
```

---

# 📂 Input File

The script expects a **CSV file containing drug names**.

Example file:

```
Removed duplicates ANOVA.csv
```

The script automatically:

* Reads the **first column**
* Extracts **unique drug names**

### Example Input Format

```
DrugName
Gefitinib
Cisplatin
Methotrexate
Docetaxel
```

---

# 🔬 How the Script Works

### Step 1

Load the CSV file containing drug names.

### Step 2

Extract unique drug names.

### Step 3

Query the **PubChem database** for each drug using **PubChemPy**.

### Step 4

Retrieve the **canonical SMILES string**.

### Step 5

Format each compound as:

```
SMILES DrugName
```

### Step 6

Split the results into **batches of 100 compounds**.

### Step 7

Save batch files for **SwissADME submission**.

---

# 📤 Output Files

The script generates **SwissADME-formatted batch files**.

### Example Output Files

```
SwissADME_Batch_1.txt
SwissADME_Batch_2.txt
SwissADME_Batch_3.txt
```

### Example File Content

```
COC1=C(C=C2C(=C1)N=CN=C2NC3=CC(=C(C=C3)F)Cl)OCCCN4CCOCC4 Gefitinib
N.N.Cl[Pt]Cl Cisplatin
CN(CC1=CN=C2C(=N1)C(=NC(=N2)N)N)C3=CC=C(C=C3)C(=O)NC Methotrexate
```

These files can be **directly pasted or uploaded to the SwissADME web server**.

---

# ▶️ Usage

Run the script using **Python** or **Jupyter Notebook**.

### Example

```
python smiles_conversion.py
```

Or run the notebook in **Google Colab**.

Once completed, the script will **generate SwissADME batch files in the working directory**.

---

# 🔁 Example Workflow

```
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
```

---

# 🧬 Applications

This tool can be used in:

* Drug discovery pipelines
* ADME property prediction
* Cheminformatics data preparation
* High-throughput screening workflows
* Computational pharmacology research

---

# ⚠️ Error Handling

If a **drug name cannot be found in PubChem**, the script:

* Records the compound in a **failed drug list**
* Continues processing the **remaining compounds**

This ensures the **pipeline runs without interruption**.

---

# 🚀 Future Improvements

Possible future enhancements include:

* Support for additional chemical databases

  * ChEMBL
  * DrugBank

* Automatic **SwissADME submission integration**

* **Parallel processing** for faster compound retrieval

* Export formats for:

  * Docking software
  * Molecular modeling tools

---

# 👨‍💻 Author

Developed for **computational biology and drug discovery workflows**.

---

# 📜 License

This project is **open source** and available under the **MIT License**.
