# Detection-of-Phishing-URLs
# Phishing URL Dataset Preparation

This project demonstrates the preparation and splitting of a phishing URL dataset for machine learning experiments. It includes **data cleaning, normalization, and creating train, validation, and test sets**.

---

## Dataset

- **Source:** `PhiUSIIL_Phishing_URL_Dataset.csv`  
- **Columns used:**  
  - `URL` → the website link  
  - `label` → indicates if the URL is **phishing (1)** or **legitimate (0)**  

---

## Steps Performed

1. **Load Dataset**  
   - The CSV file is read using `pandas`.  

2. **Check Label Distribution**  
   - Counted how many phishing vs legitimate URLs exist.  
   - This helps ensure the dataset is **not highly imbalanced**.  

3. **Select Relevant Columns**  
   - Only the `URL` and `label` columns are retained for simplicity.  

4. **Data Cleaning**  
   - Removed duplicate URLs.  
   - Dropped rows with missing `URL` or `label`.  
   - Normalized URLs:  
     - Converted to lowercase  
     - Removed extra spaces  

5. **Dataset Splitting**  
   - **First split:** Train + Validation vs Test (80% / 20%)  
   - **Second split:** Train vs Validation (80% / 20% of the 80%)  
   - Ensured **stratified splits**, so each set maintains the same proportion of phishing and legitimate URLs.  

6. **Reset Indices**  
   - Reset the DataFrame indices for clean, sequential indexing.  

---

## Final Dataset

- **Train set:** Used to train models  
- **Validation set:** Used to tune hyperparameters  
- **Test set:** Used to evaluate model performance  

**Example class distribution:**
Train class distribution:
phishing XXX
legitimate XXX

Validation class distribution:
phishing XXX
legitimate XXX

Test class distribution:
phishing XXX
legitimate XXX


*(Note: `XXX` represents the number of URLs in each category.)*

---

## How to Use

1. Load the CSV file into a Python environment.  
2. Run the preprocessing script.  
3. Use `train.csv`, `val.csv`, and `test.csv` for your machine learning pipeline.  

---

## Notes

- This preparation ensures **balanced and clean data** for model training.  
- URLs are normalized to **prevent duplicates due to case differences**.  
- Stratified splitting guarantees that each set has a **representative distribution** of phishing and legitimate URLs.  

