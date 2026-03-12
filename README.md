# Lab 2.2 — CO2 Emissions Linear Regression

## Objective

Is notebook mein **Canada ke vehicles ka CO2 emissions data** use karke ek **Linear Regression model** train kiya gaya hai jo engine size aur fuel consumption se CO2 emissions predict karta hai.

---

## Dataset

**File:** `CO2 Emissions.csv`

| Property | Value |
|----------|-------|
| Total Records | 7,385 |
| Total Features | 12 |
| Missing Values | 0 (clean dataset) |

### Columns

| Column Name | Type | Description |
|---|---|---|
| `Make` | object | Car manufacturer (e.g., ACURA, BMW) |
| `Model` | object | Car model name |
| `Vehicle Class` | object | Type of vehicle (e.g., COMPACT, SUV) |
| `Engine Size(L)` | float64 | Engine size in litres |
| `Cylinders` | int64 | Number of cylinders |
| `Transmission` | object | Transmission type |
| `Fuel Type` | object | Type of fuel used |
| `Fuel Consumption City (L/100 km)` | float64 | City fuel consumption |
| `Fuel Consumption Hwy (L/100 km)` | float64 | Highway fuel consumption |
| `Fuel Consumption Comb (L/100 km)` | float64 | Combined fuel consumption |
| `Fuel Consumption Comb (mpg)` | int64 | Combined fuel consumption in mpg |
| `CO2 Emissions(g/km)` | int64 | **Target variable** — CO2 emissions in g/km |

---

## Analysis Performed

### 1. Data Loading & Inspection ✅
- Dataset CSV load kiya
- `df.head()` se pehle 5 rows dekhe
- `df.info()` se data types aur null values check kiye
- `df.describe()` se statistical summary nikali

### 2. Missing Value Check ✅
- Koi missing value nahi mili — dataset bilkul clean hai

### 3. EDA (Exploratory Data Analysis) ✅
- **Correlation Heatmap** — `seaborn` se numerical features ka correlation dekha (`coolwarm` colormap)
- **Pairplot** — sabhi numerical features ke beech scatter plots aur KDE distributions

### 4. Feature Selection ✅
| Role | Feature |
|------|---------|
| Input (X) | `Engine Size(L)`, `Fuel Consumption Comb (L/100 km)` |
| Target (y) | `CO2 Emissions(g/km)` |

### 5. Train-Test Split ✅
- `test_size = 0.2` (80% train, 20% test)
- `random_state = 42`

### 6. Model Training ✅
- **Algorithm:** Linear Regression (`sklearn`)

### 7. Model Evaluation ✅
| Metric | Score |
|--------|-------|
| Mean Absolute Error (MAE) | 13.51 |
| Mean Squared Error (MSE) | 443.24 |
| R² Score | **0.871** |

> R² = 0.871 matlab model **87.1% variance** explain kar raha hai — kaafi accha result hai!

### 8. Visualization ✅
- **Actual vs Predicted CO2 Emissions** scatter plot banaya

---

## Key Findings

- **Engine size aur fuel consumption** mein CO2 emissions ke saath strong positive correlation hai
- Jitna bada engine aur jitna zyada fuel consumption, utna zyada CO2 emissions
- Linear Regression model ne **87% accuracy** achieve ki sirf 2 features se

---

## How to Run

```bash
# 1. Dataset file ko notebook ke saath same folder mein rakh
# CO2 Emissions.csv

# 2. Dependencies install karo
pip install pandas numpy matplotlib seaborn scikit-learn

# 3. Jupyter Notebook chalao
jupyter notebook Lab2_2.ipynb
```

---

## Tech Stack

| Library | Usage |
|---------|-------|
| `pandas` | Data loading aur manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Plotting |
| `seaborn` | Advanced visualizations (heatmap, pairplot) |
| `scikit-learn` | Train-test split, Linear Regression, evaluation metrics |

---

## File Structure

```
Lab2_2/
├── Lab2_2.ipynb          # Main notebook
├── CO2 Emissions.csv     # Dataset
└── README.md             # Yeh file
```

---

## Dataset Source

**Canada CO2 Emissions Dataset** — vehicles ka fuel consumption aur CO2 emissions data.  
Available on [Kaggle](https://www.kaggle.com/datasets/debajyotipodder/co2-emission-by-vehicles).
