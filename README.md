# Algerian Forest Fire Prediction

This project focuses on predicting the Fire Weather Index (FWI) using various regression models. The dataset used is specific to Algerian forest fires, with historical weather data and fire occurrences.

## Overview

The goal of this project is to create an effective prediction model for FWI using different regression techniques. This involves data preprocessing, feature selection, model training, evaluation, and fine-tuning.

Here's the updated README.md section incorporating the information about the HTML web page used for deployment:

---

## Dataset Information

The dataset used in this project consists of 244 instances, gathered from two regions in Algeria: Bejaia, located in the northeast, and Sidi Bel-abbes, located in the northwest. The data covers the period from June 2012 to September 2012, with 122 instances for each region. 

### Features:

1. **Date**: Day, month (June to September), and year (2012).
2. **Temperature**: Noon temperature (max temperature) in Celsius degrees, ranging from 22°C to 42°C.
3. **Relative Humidity (RH)**: Ranges from 21% to 90%.
4. **Wind Speed (Ws)**: Ranges from 6 km/h to 29 km/h.
5. **Rain**: Total daily rainfall in mm, ranging from 0 to 16.8 mm.
6. **Fine Fuel Moisture Code (FFMC)**: Index from the FWI system, ranging from 28.6 to 92.5.
7. **Duff Moisture Code (DMC)**: Index from the FWI system, ranging from 1.1 to 65.9.
8. **Drought Code (DC)**: Index from the FWI system, ranging from 7 to 220.4.
9. **Initial Spread Index (ISI)**: Index from the FWI system, ranging from 0 to 18.5.
10. **Buildup Index (BUI)**: Index from the FWI system, ranging from 1.1 to 68.
11. **Fire Weather Index (FWI)**: The primary target variable, ranging from 0 to 31.1.
12. **Classes**: Binary classification with two classes—'fire' and 'not fire'.

### Data Preprocessing:

- **Region Assignment**: The dataset is split into two subsets: "Bejaia Region Dataset" and "Sidi-Bel Abbes Region Dataset". Rows until the 122nd index correspond to the Bejaia region (labeled as 0), and rows from the 123rd index onward correspond to the Sidi-Bel Abbes region (labeled as 1).
- **Handling Missing Values**: Missing values were identified and removed, and the dataset was reset to ensure consistency.
- **Column Adjustments**: Unnecessary columns (e.g., 'day', 'month', 'year') were removed. Column names were stripped of any leading or trailing whitespace, and data types were converted for consistency.
- **Class Encoding**: The 'Classes' column was encoded into binary format, where 'not fire' was mapped to 0, and 'fire' was mapped to 1.

### Exploratory Data Analysis (EDA):

- **Distribution Analysis**: The dataset was visualized using histograms and boxplots to understand the distribution of features.
- **Correlation Analysis**: A heatmap was generated to visualize the correlation between different features, with particular attention to multicollinearity.
- **Fire Occurrence**: The occurrence of fires was analyzed through a pie chart and monthly fire analysis for each region using count plots.

### Data Cleaning Output:

- A cleaned version of the dataset was saved as `ALgerian_forest_fires_cleaned.csv` for further analysis and modeling.

### Model Training and Evaluation:

- Various regression models were trained and evaluated, including Linear Regression, Lasso Regression, Ridge Regression, and Elastic Net Regression. Various Cross validation models are also used to check adjacent improvements. Performance metrics such as Mean Absolute Error (MAE) and R-2 Score were computed to assess the models.

### Flask Web Application

A Flask web application is provided for making predictions using the trained regression model. The application includes:

1. **Flask Setup**:
   - Imports necessary libraries including Flask, NumPy, and Pandas.
   - Loads the trained regression model and scaler using Pickle.

2. **Routes**:
   - **`/`**: Renders a simple HTML page (`home.html`) for user interaction.
   - **`/predict_api`**: Accepts JSON data for prediction via an API request. The input data is scaled and fed into the regression model to obtain a prediction, which is then returned as a JSON response.
   - **`/predict`**: Accepts form data for prediction via a POST request. The input data is scaled and fed into the regression model, and the prediction is rendered on the HTML page.

3. **HTML Page**:
   - A simple HTML page (`home.html`) is used for user interaction, allowing users to input data and view predictions.

4. **Running the Application**:
   - The application runs in debug mode, allowing for real-time updates and debugging during development.

## Getting Started

### Prerequisites

- Python 3.x
- Libraries: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

### Installation

```bash
pip install -r requirements.txt
```

### Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/algerian-forest-fire-prediction.git
   ```
2. Run the script:
   ```bash
   python main.py
   ```

## File Structure

- `app.py`: Main script to run the project.
- `scaling.pkl`: Pickled scaler file.
- `regmodel.pkl`: Pickled regression model.
- `requirements.txt`: File carrying the information  of all the dependencies used in the project.
- `Data Preparation.ipynb`: Jupyter source file used for data cleaning and preprocessing.
- `ML model.ipynb`:  Jupyter source file used for data modelling and evaluation.
- `README.md`: Project overview and instructions.
