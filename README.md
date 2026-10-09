# House Price Analytics & Prediction

**Author:** Amir Muaviya Khan
**Program:** AICTE | IBM SkillsBuild Data Analytics with AI Internship 2026 (BharatCares)

## Project Description
A real-estate business wants to know **what drives house prices** and how to **predict the sale price** of a house. This project cleans the data, calculates key KPIs, explores it with charts (EDA), builds a prediction model, and ends with risks, opportunities and recommended business actions.

Flow: `Data -> Cleaning -> KPIs -> EDA -> Prediction Model -> Insights -> Recommended Actions`

## Dataset
- **Name:** House Prices - Advanced Regression Techniques (1,460 houses, 81 columns)
- **Source (Kaggle):** https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques
- **File used:** `train.csv`

Download `train.csv` from the link above and place it in the same folder as the notebook.

## Key Results
| KPI | Value |
|---|---|
| Average sale price | $180,921 |
| Median sale price | $163,000 |
| Average price per sq. ft. | $120.6 |
| Priciest neighbourhood (10+ sales) | NoRidge (avg $335,295) |

- Overall quality is the strongest driver: quality-8 houses sell for about **2.1x** the price of quality-5 houses.
- Best model: **Ridge Regression**, R2 = **0.92** on the test data (about 0.85 in 5-fold cross-validation), average error about **$16,155** per house.

## Technologies Used
Python 3, pandas, NumPy, Matplotlib, Seaborn, scikit-learn (Ridge Regression, Random Forest, Gradient Boosting), Jupyter Notebook

## Project Files
| File | Purpose |
|---|---|
| `AmirMuaviyaKhan_HousePrice.ipynb` | Complete code with outputs and charts |
| `requirements.txt` | Python libraries needed |
| `README.md` | This overview |
| `AmirMuaviyaKhan_ProjectReport.docx` | Full project report |

## Setup & Run Instructions
**Option 1: Google Colab (easiest)**
1. Open https://colab.research.google.com and choose *File -> Upload notebook*, then select `AmirMuaviyaKhan_HousePrice.ipynb`.
2. Upload `train.csv` using the folder icon on the left.
3. Choose *Runtime -> Run all*.

**Option 2: Local computer**
1. Install Python 3.9 or newer.
2. Install the libraries: `pip install -r requirements.txt`
3. Put `train.csv` in the same folder as the notebook.
4. Start Jupyter with `jupyter notebook` and open `AmirMuaviyaKhan_HousePrice.ipynb`.
5. Choose *Run -> Run All Cells*. Charts are saved in a `charts/` folder.

## Key Information
- Many "missing" values (for example no pool, no alley, no garage) mean the feature does not exist, so they are filled with `"None"` rather than treated as errors.
- `PricePerSqFt` is used only for the KPI and charts. It is **excluded** from the model because it is calculated from the price itself (this would leak the answer).
- The target (`SalePrice`) is log-transformed for modelling because prices are skewed.
- The model uses only the features in this dataset, so it should be retrained with fresh sales data over time.
