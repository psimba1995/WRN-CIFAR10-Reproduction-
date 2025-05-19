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

## Project Structure

WRN-CIFAR10-Reproduction-/
│
├── notebooks/
│ ├── 01_data_preprocessing_cynthia.ipynb
│ ├── 02_model_building_paida.ipynb
│ ├── 03_training_paida.ipynb
│ └── 04_evaluation_zaid.ipynb
├── README.md
└── .gitignore


## ⚙️ Setup Instructions (Reproducibility)

> ✅ Tested on macOS and Linux.  
> Python 3.9 or above is recommended.

### 1. Clone the repository

```bash
git clone https://github.com/psimba1995/WRN-CIFAR10-Reproduction-.git
cd WRN-CIFAR10-Reproduction-\
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
