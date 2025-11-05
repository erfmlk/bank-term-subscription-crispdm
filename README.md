#  Bank Term Deposit Subscription Prediction Using CRISP-DM
### Project for Assignment 17.1 – Comparing Classifiers  
**Course:** Professional Certificate in Machine Learning & AI – University of California Berkeley  
**By:**  Erfan Maleki  

---

##  Overview
This project analyzes telephone-marketing campaign data from a Portuguese banking institution to predict whether a client will subscribe to a **term deposit**.  
The workflow follows the **CRISP-DM** (Cross-Industry Standard Process for Data Mining) methodology — guiding every phase from **business understanding** to **model evaluation** and **deployment recommendations**.

---

##  Objective
Develop a supervised-learning pipeline that:

- Predicts client subscription outcomes (`yes / no`)  
- Identifies the most influential campaign and economic factors  
- Optimizes call-center strategy and marketing efficiency  

---

##  Dataset Details
**Source:** [UCI Machine Learning Repository – Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing)  
**File Used:** `bank-additional-full.csv`  
**Size:** 41 188 rows × 21 columns  
**Target:** `y` (1 = subscribed, 0 = not subscribed)  
**Imbalance:** ≈ 88 % No  |  12 % Yes  

###  Feature Groups
| Category | Examples |
|-----------|-----------|
| Demographics | `age`, `job`, `marital`, `education` |
| Financial Status | `default`, `housing`, `loan` |
| Campaign Attributes | `contact`, `month`, `day_of_week`, `duration` |
| Performance History | `campaign`, `pdays`, `previous`, `poutcome` |
| Economic Indicators | `emp.var.rate`, `cons.price.idx`, `euribor3m`, `nr.employed` |

---

## 🛠️ Tools & Libraries
- **Python 3.10+**  
- `pandas`, `numpy` – data handling  
- `matplotlib`, `seaborn` – visualization  
- `scikit-learn` – modeling & evaluation  
- `missingno` – data completeness plots  
- **Jupyter Notebook** – interactive analysis  

---

##  CRISP-DM Methodology
1. **Business Understanding** – define objectives & success criteria  
2. **Data Understanding** – explore campaign data and detect patterns  
3. **Data Preparation** – clean and encode features  
4. **Modeling** – train and tune KNN, Logistic Regression, Decision Tree, SVM  
5. **Evaluation** – compare AUC, ROC, Precision-Recall, Lift  
6. **Deployment** – translate results into business strategy  

![CRISP-DM Flow](A_cross-industry_standard_process_for_data_mining.png)

---

##  Exploratory Insights
- **Call Duration Matters:** longer calls (> 300 s) strongly increase subscription likelihood.  
- **Timing:** highest success in March, June, September, December.  
- **Financial Stability:** clients without loans convert more often.  
- **Economic Trends:** low `euribor3m` rates boost confidence.  

---

##  Model Comparison

| Model | AUC | Accuracy | Best Params |
|:--|:--:|:--:|:--|
| KNN | 0.84 | 0.89 | n_neighbors = 5 |
| Logistic Regression | 0.88 | 0.90 | C = 1 |
| Decision Tree | 0.86 | 0.91 | max_depth = 10 |
| **SVM (RBF)** | **0.94** | **0.92** | C = 1, kernel = `rbf` |

** Best Model:** SVM (RBF) — excellent generalization and handling of imbalanced classes.  

---

##  Visualizations
Key figures (see `/images` or `.zip` folder):

1. Target class distribution  
2. Age & job distributions  
3. Correlation heatmap  
4. Call duration vs outcome  
5. Monthly success trend  
6. ROC & Precision–Recall curves (4 models)  
7. AUC bar chart comparison  
8. Confusion matrix (SVM)  
9. Lift curve (marketing effectiveness)  
10. Feature importance (LogReg & Tree)  
11. Combined dashboard summary  

---

##  Actionable Business Insights
- **Prioritize Quality Engagement:** Encourage longer, meaningful calls.  
- **Schedule Strategically:** Focus on end-of-quarter months.  
- **Target Financially Stable Clients:** Avoid active loan holders.  
- **Integrate Predictive AI:** Use SVM scores in CRM for lead ranking.  
- **Automate Retraining:** Update models quarterly to reflect new economic data.  
- **Efficiency Gain:** Reduce cold calls by ≈ 50 % without losing yield.  

---

##  Deliverables
| File | Description |
|------|--------------|
| `Capstone17_1_Final.ipynb` | Full Jupyter Notebook with code and analysis |
| `Capstone17_1_Final_Report.pdf` | Written report summary |
| `Capstone17_1_All_Diagrams.zip` | 22 EDA and model figures |
| `README.md` | GitHub project summary (this file) |

---

##  How to Run
```bash
# Clone the repository
git clone https://github.com/erfmlk/bank-term-subscription-crispdm.git
cd bank-term-subscription-crispdm

# Open the notebook
jupyter notebook Capstone17_1_Final.ipynb
