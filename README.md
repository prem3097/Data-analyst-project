# Data-analyst-project

# 🧼 Laptop Data Cleaning and Preprocessing

This project focuses on **data cleaning and preprocessing** of a dataset containing specifications and attributes of various laptops. The cleaned dataset will serve as a foundation for further analysis, visualization, or machine learning applications.

## 📁 Dataset Overview

The dataset (`laptopData.csv`) includes the following features:

- **Company**: Laptop manufacturer
- **TypeName**: Category (e.g., Ultrabook, Gaming)
- **Inches**: Screen size
- **ScreenResolution**, **Cpu**, **Ram**, **Memory**, **Gpu**, **OpSys**, **Weight**
- **Price**: Target variable (in some versions of the dataset)

---

## 📊 Cleaning & Preprocessing Workflow

The entire cleaning process is performed in the Jupyter Notebook: `laptopclean.ipynb`.

### 1. 📦 Importing Libraries
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
````

### 2. 📄 Loading the Dataset

```python
df = pd.read_csv('/content/laptopData.csv')
```

* Loaded data into a pandas DataFrame.

### 3. 🧠 Initial Data Exploration

* Used `df.info()` to inspect data types and missing values.
* Verified the number of rows, columns, and null entries.

### 4. ❌ Handling Missing & Invalid Values

* Replaced `'No OS'` in the `OpSys` column and `'?'` in the `Weight` column with `NaN`.
* Checked total missing values per column.

### 5. 🔄 Imputing Missing Values

* Replaced `NaN` values with the **most frequent (mode)** values in columns such as:

  * `Company`
  * `TypeName`
  * `Inches`
  * `Weight`
  * `OpSys`

```python
x = df["Company"].mode()[0]
df.fillna({"Company": x}, inplace=True)
```

### 6. 🧹 Dropping Redundant Columns

* Removed an unnecessary index column: `Unnamed: 0`.

```python
df.drop("Unnamed: 0", axis=1, inplace=True)
```

### 7. 🧬 Removing Duplicate Records

* Detected and dropped duplicate rows.
* Reset the DataFrame index to ensure consistency.

```python
df.drop_duplicates(inplace=True)
df.reset_index(drop=True, inplace=True)
```

---

## 📈 Future Work

* Perform **data visualization** using Seaborn/Matplotlib.
* Conduct **feature engineering** (e.g., parsing CPU and GPU text).
* Train **machine learning models** to predict laptop prices or categorize types.
* Export the cleaned data to a new CSV for external use.

---

## 🛠️ Installation

Clone this repository and install required packages:

```bash
git clone https://github.com/yourusername/laptop-cleaning-project.git
cd laptop-cleaning-project
pip install pandas numpy matplotlib seaborn jupyter
```

---

## 🚀 Usage

Run the notebook using Jupyter:

```bash
jupyter notebook laptopclean.ipynb
```

---

## 📚 Dependencies

* Python 3.x
* pandas
* numpy
* matplotlib
* seaborn
* jupyter

You can also create a virtual environment and install these packages using:

```bash
pip install -r requirements.txt
```

---

## 📌 License

This project is licensed under the MIT License.

---

## 🙋‍♂️ Author

**Your Name**
[GitHub](https://github.com/prem3097) | [LinkedIn](https://www.linkedin.com/in/premkumar-r-ba4a002a1?)

---
