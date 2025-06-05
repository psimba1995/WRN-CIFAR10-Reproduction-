# WRN-CIFAR10-Reproduction-

This project reproduces the results of the paper  
**"Wide Residual Networks" by Zagoruyko & Komodakis (2016)**  
on the CIFAR-10 image classification dataset.

The key idea is to improve on traditional ResNets by **increasing width (channels)** instead of going deeper.

---

## 👥 Team Members

- **Cynthia Nyahoda** – Data preprocessing, reproducibility setup, GitHub management  
- **Paidamoyo Simba** – WRN model building, training, tuning  
- **Zaid Alotel** – Evaluation, analysis, result comparison

---


## 📂 Project Structure

The repository is organized as follows:

```
WRN-CIFAR10-Reproduction-/
│
├── notebooks/                   # Jupyter notebooks for various stages of the project
│   ├── 01_data_preprocessing_cynthia.ipynb  # Data preprocessing
│   ├── 02_model_building_paida.ipynb       # Model building
│   ├── 03_training_paida.ipynb             # Model training
│   └── 04_evaluation_zaid.ipynb            # Model evaluation
│
├── README.md                    # Project overview and instructions
├── requirements.txt             # Python dependencies for reproducibility
├── .gitignore                   # Files and folders to ignore in the repository
└── .gitattributes               # Git configuration for the repository
```

### 📝 Notes
- Each `.ipynb` notebook corresponds to a specific step in the process: preprocessing, model building, training, and evaluation.
- All results, including training metrics and plots, are saved and displayed in the respective notebooks.

## ⚙️ Setup Instructions (Reproducibility)

> ✅ Tested on macOS, Linux, and Windows.  
> Python 3.9 or above is recommended.

1. **Clone the repository**:
   ```bash
   git clone https://github.com/psimba1995/WRN-CIFAR10-Reproduction-.git
   cd WRN-CIFAR10-Reproduction-
   ```

2. **Set up the Python environment**:
   - It is recommended to use a virtual environment:
     ```bash
     python3.9 -m venv wrn_env
     source wrn_env/bin/activate
     ```
   - Install all dependencies:
     ```bash
     pip install -r requirements.txt
     ```

3. **Verify installation**:
   - Ensure that all required libraries are installed and the Python version is correct:
     ```bash
     python --version
     pip list
     ```

4. **Download CIFAR-10 dataset automatically**:
   - The dataset will be downloaded automatically the first time the script is run via `torchvision`.

---
## 🚀 How to Run

1. **Data Preprocessing**:
   Run the first notebook to preprocess the CIFAR-10 dataset:
   ```bash
   jupyter notebook notebooks/01_data_preprocessing_cynthia.ipynb
   ```

2. **Model Building**:
   Build the Wide Residual Network model by executing the second notebook:
   ```bash
   jupyter notebook notebooks/02_model_building_paida.ipynb
   ```

3. **Model Training**:
   Train the WRN model on CIFAR-10 by running the training notebook:
   ```bash
   jupyter notebook notebooks/03_training_paida.ipynb
   ```

4. **Evaluate the Model**:
   Evaluate the trained model and compare the results with the original paper:
   ```bash
   jupyter notebook notebooks/04_evaluation_zaid.ipynb
   ```

## Expected Results

WRN-28-10 achieves ~84–85% accuracy on CIFAR-10 (10 epochs)
Accuracy improves steadily with depth and width
Confirmed author’s claim: wider can be better than deeper

## Reference

Paper: https://arxiv.org/abs/1605.07146
Code: yu4u/wide-resnet-pytorch

## Reproducibility 

This project follows best practices for reproducible research:

Each contribution is version-controlled on GitHub
Git branches were used for team member contributions
Python environment dependencies are listed and documented
CIFAR-10 is auto-downloaded through torchvision
Results (training metrics and plots) are embedded in .ipynb notebooks



---
### 🎯 Final Evaluation: Reproduction vs. Original WRN Results

This section compares the performance of our reproduced Wide Residual Network (WRN-28-10) on the CIFAR-10 dataset to the original results reported by Zagoruyko & Komodakis (2016).

---

### ✅ Reported Results from Original Paper:

* **Dataset**: CIFAR-10
* **Model**: WRN-28-10
* **Top-1 Test Accuracy**: **95.83%**
* **Training Strategy**: SGD with momentum, learning rate schedule, weight decay, and data augmentation

---

### ⌚ Reproduced Results:

* **Model**: WRN-28-10 (same architecture)
* **Best Accuracy Achieved**: **\~89.4%** (after 10 epochs)
* **Evaluation Outputs**:

  * Accuracy: **0.84**
  * Macro Avg F1-score: **0.84**
  * Weighted Avg F1-score: **0.84**
  * Output Files: `confusion_matrix.npy`, `classification_report.txt`
* **Class-wise Strengths**:

  * Highest precision: **automobile (0.96)**, **ship (0.95)**
  * Highest recall: **truck (0.97)**, **airplane (0.94)**
---

| Value        | Meaning                                                | Source                       |
| ------------ | ------------------------------------------------------ | ---------------------------- |
| **95.83%**   | Full WRN-28-10 result from original paper (200 epochs) | Zagoruyko & Komodakis (2016) |
| **84–89.4%** | Our reproduced result (10 epochs)                      | our GitHub repo & output    |

---

### 🔍 Observations & Analysis

* **Accuracy Gap**: Our accuracy (\~89.4%) is below the original 95.83%, likely due to:

  * Shorter training duration (10 epochs vs. 200 in original)
  * Limited compute power and epochs
  * Possible absence of advanced regularization or ensembling

* **Model Behavior**:

  * Performance increased steadily across epochs (verified via our training notebook)
  * Final accuracy and F1-score reflect solid generalization despite reduced training time

* **Hypothesis Validation**:

  * Even with constraints, WRN-28-10 achieved strong performance, supporting the authors' claim that **width helps generalization** and **faster convergence**.

---

### 📄 Reproducibility Assessment

* The original authors provided high-quality code and clear architectural design
* Our use of GitHub, modular notebooks, and saved outputs made reproduction structured and replicable
* Intermediate and final results (e.g., confusion matrix, `.pth` weights) show traceability and transparency

---

### ✅ Conclusion

Our reproduction affirms the key findings of the WRN paper: wider residual blocks provide strong accuracy gains and allow for faster learning. While our results are slightly lower due to limited training time, the pipeline successfully demonstrated that **the approach is reproducible**, practical, and effective.




