# 🚗 Car Price Prediction

Predict the **selling price of used cars** from features like year, present price, kilometres driven, fuel type, seller type, transmission and number of owners. The notebook compares **Linear Regression** and **Lasso Regression** using scikit-learn.

## 📊 Dataset

[Vehicle Dataset from CarDekho](https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho) (Kaggle). This project uses `car data.csv`, which has 301 rows and 9 columns.

| Column | Description |
|---|---|
| `Car_Name` | Car model name (dropped before training) |
| `Year` | Year of manufacture |
| `Selling_Price` | **Target**: selling price (lakhs) |
| `Present_Price` | Current ex-showroom price (lakhs) |
| `Kms_Driven` | Kilometres driven |
| `Fuel_Type` | Petrol = 0, Diesel = 1, CNG = 2 |
| `Seller_Type` | Dealer = 0, Individual = 1 |
| `Transmission` | Manual = 0, Automatic = 1 |
| `Owner` | Number of previous owners |

## 🔧 Workflow

1. Load the data and check for missing values (there are none).
2. Encode the categorical columns with `map`.
3. Split features and target, then make an 80/20 train/test split (`random_state=1`).
4. Train a **Linear Regression** model and evaluate it with R².
5. Train a **Lasso Regression** model and evaluate it with R².
6. Plot actual vs predicted prices for train and test sets.

## 📈 Results

| Model | Train R² | Test R² |
|---|---|---|
| Linear Regression | 0.880 | 0.848 |
| Lasso Regression | 0.842 | **0.854** |

Lasso fits the training data a little less closely but generalises slightly better to unseen cars.

## 🚀 How to run

**On Kaggle:** open the notebook and add the CarDekho dataset as input, then run all cells.

**Locally:**

```bash
git clone https://github.com/GuninderSinghBhatia/car-price-prediction.git
cd car-price-prediction
pip install -r requirements.txt
jupyter notebook car_price_prediction.ipynb
```

Download `car data.csv` from Kaggle and change the path in the `pd.read_csv(...)` cell to where you saved it.

## 📁 Project structure

```
car-price-prediction/
├── car_price_prediction.ipynb   # Full analysis and models
├── requirements.txt             # Python dependencies
├── README.md
├── LICENSE                      # MIT
└── .gitignore
```

## 🛠️ Tech stack

Python · pandas · scikit-learn · matplotlib · seaborn · Jupyter / Kaggle

## 🔮 Future improvements

- Add a `Car_Age` feature (current year − `Year`)
- Try Ridge, Random Forest and XGBoost
- Tune Lasso `alpha` with cross-validation
- Report MAE / RMSE alongside R²

## 📜 License

MIT. See [LICENSE](LICENSE).
