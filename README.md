\# Sales Forecasting System



A data science project that analyzes historical retail sales and predicts future daily sales using machine learning.



The project covers data cleaning, exploratory data analysis, time-based feature engineering, model training, prediction, and evaluation.



\## Project Objectives



\- Load and inspect historical sales data from a CSV file

\- Handle missing values and duplicate records

\- Convert date values into the correct data type

\- Analyze sales trends over time

\- Identify the highest and lowest sales months

\- Examine monthly and seasonal sales patterns

\- Create time-based features from dates

\- Train and compare regression models

\- Predict future sales for a chronological test period

\- Evaluate predictions using MAE and RMSE



\## Dataset



The project uses the \[Superstore Sales Dataset](https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting) from Kaggle.



The original dataset contains:



\- 9,800 sales records

\- Order dates from 2015 to 2018

\- Sales, product, category, customer, shipping, and location information



The analysis retains the following relevant columns:



\- `Order Date`

\- `Sales`

\- `Category`

\- `Sub-Category`

\- `Region`



The dataset is stored at:



```text

data/train.csv

```



The dataset remains subject to the terms specified by its original Kaggle source.



\## Project Structure



```text

Sales\_forecasting\_System/

├── data/

│   └── train.csv

├── notebooks/

│   └── sales\_forecasting.ipynb

├── .gitignore

└── README.md

```



\## Project Workflow



\### 1. Data Inspection



\- Loaded the CSV file with Pandas

\- Inspected the dataset shape, columns, and data types

\- Reviewed the first records

\- Counted missing values

\- Checked fully duplicated rows



\### 2. Data Cleaning



\- Converted `Order Date` from text to `datetime`

\- Confirmed that no fully duplicated rows were present

\- Retained only the columns required for analysis and forecasting

\- Removed the missing-value issue by excluding the unnecessary `Postal Code` column



\### 3. Exploratory Data Analysis



The notebook analyzes:



\- Monthly sales trends

\- Highest and lowest sales months

\- Average sales by calendar month

\- Sales across the four seasons

\- Monthly sales patterns across different years



Both line charts and bar charts are used.



\### 4. Feature Engineering



Individual transactions are aggregated into daily total sales.



The following date-based features are created:



\- `Year`

\- `Month`

\- `Day`

\- `DayOfWeek`

\- `IsWeekend`



Days without transaction records are treated as zero-sales days to create a continuous daily time series.



\### 5. Model Building



Two Scikit-learn regression models are trained:



\- Linear Regression

\- Random Forest Regressor



The data is divided chronologically:



\- First 80%: training data

\- Most recent 20%: testing data



The chronological order is preserved to simulate forecasting future sales.



\### 6. Model Evaluation



The models are evaluated using:



\- MAE — Mean Absolute Error

\- RMSE — Root Mean Square Error



| Model | MAE | RMSE |

|---|---:|---:|

| Linear Regression | 1,673.49 | 2,420.88 |

| Random Forest | 1,816.16 | 2,644.69 |



Lower values indicate better performance. Linear Regression achieved the lowest MAE and RMSE and was selected as the final model.



\## Key Findings



\- November 2018 had the highest monthly sales.

\- February 2015 had the lowest monthly sales.

\- Sales generally increased in September and November.

\- A decline was commonly observed in October.

\- Autumn had the highest average monthly sales.

\- Adding weekday and weekend information slightly improved both models.

\- Linear Regression performed better than Random Forest on the future test period.



\## Actual vs Predicted Sales



The selected Linear Regression model generates daily sales predictions for the chronological test period.



The notebook compares:



\- Order date

\- Actual daily sales

\- Predicted daily sales

\- Absolute prediction error



This comparison shows where the model performs well and where sudden sales changes create larger errors.



\## Limitations



\- Daily sales are highly variable.

\- Some days contain no sales records.

\- The models use only date-based features.

\- Promotions, holidays, and external business factors are not available.

\- Sudden sales peaks are difficult to predict with the available features.



\## Technologies



\- Python

\- Pandas

\- NumPy

\- Matplotlib

\- Scikit-learn

\- Jupyter Notebook



\## How to Run



Clone the repository:



```powershell

git clone https://github.com/Ardatatl33/Sales\_forecasting\_System.git

cd Sales\_forecasting\_System

```



Start Jupyter Notebook:



```powershell

python -m notebook

```



Open:



```text

notebooks/sales\_forecasting.ipynb

```



Then select:



```text

Kernel → Restart Kernel and Run All Cells

```



\## Repository



\[GitHub Repository](https://github.com/Ardatatl33/Sales\_forecasting\_System)

