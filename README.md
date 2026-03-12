Lab 2.2 — CO2 Emissions Linear Regression
Objective
This notebook uses Canada's vehicle CO2 emissions data to train a Linear Regression model that predicts CO2 emissions from engine size and fuel consumption.

Dataset
File: CO2 Emissions.csv
PropertyValueTotal Records7,385Total Features12Missing Values0 (clean dataset)
Columns
Column NameTypeDescriptionMakeobjectCar manufacturer (e.g., ACURA, BMW)ModelobjectCar model nameVehicle ClassobjectType of vehicle (e.g., COMPACT, SUV)Engine Size(L)float64Engine size in litresCylindersint64Number of cylindersTransmissionobjectTransmission typeFuel TypeobjectType of fuel usedFuel Consumption City (L/100 km)float64City fuel consumptionFuel Consumption Hwy (L/100 km)float64Highway fuel consumptionFuel Consumption Comb (L/100 km)float64Combined fuel consumptionFuel Consumption Comb (mpg)int64Combined fuel consumption in mpgCO2 Emissions(g/km)int64Target variable — CO2 emissions in g/km

Analysis Performed
1. Data Loading & Inspection ✅

Loaded the dataset CSV file
Viewed first 5 rows using df.head()
Checked data types and null values using df.info()
Generated statistical summary using df.describe()

2. Missing Value Check ✅

No missing values found — dataset is completely clean

3. EDA (Exploratory Data Analysis) ✅

Correlation Heatmap — visualized correlation between numerical features using seaborn (coolwarm colormap)
Pairplot — scatter plots and KDE distributions across all numerical features

4. Feature Selection ✅
RoleFeatureInput (X)Engine Size(L), Fuel Consumption Comb (L/100 km)Target (y)CO2 Emissions(g/km)
5. Train-Test Split ✅

test_size = 0.2 (80% train, 20% test)
random_state = 42

6. Model Training ✅

Algorithm: Linear Regression (sklearn)

7. Model Evaluation ✅
MetricScoreMean Absolute Error (MAE)13.51Mean Squared Error (MSE)443.24R² Score0.871

R² = 0.871 means the model explains 87.1% of the variance — a very strong result!

8. Visualization ✅

Generated an Actual vs Predicted CO2 Emissions scatter plot


Key Findings

Engine size and fuel consumption have a strong positive correlation with CO2 emissions
Larger engines and higher fuel consumption lead to higher CO2 emissions
The Linear Regression model achieved 87% accuracy using just 2 features


How to Run
bash# 1. Place the dataset file in the same folder as the notebook
# CO2 Emissions.csv

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn

# 3. Run Jupyter Notebook
jupyter notebook Lab2_2.ipynb
```

---

## Tech Stack
| Library | Usage |
|---------|-------|
| `pandas` | Data loading and manipulation |
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
└── README.md             # This file

Dataset Source
Canada CO2 Emissions Dataset — vehicle fuel consumption and CO2 emissions data.
Available on Kaggle.
