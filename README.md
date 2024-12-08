# Mastercard Credit Card Fraud Detection Challenge Project
## Introduction
#### Project Overview
This project aims to detect fraudulent credit card transactions using various machine learning algorithms. The goal is to create a model that can identify suspicious activities and prevent losses for cardholders, merchants, and financial institutions.

#### Methodology


#### Results and Key Findings


#### Visualizations


#### Potential Next Steps



## Table of Contents
* [Introduction](#introduction)
* [Data Sets](#data-sets)
* [Installation](#installation)
* [Usage](#usage)
* [Contributing](#contributing)
* [License](#license)
* [Credits and Acknowledgements](#credits-and-acknowledgements)

## Data Sets
The data used in this project is publicly sourced from Kaggle. This is a simulated credit card transaction data set containing legitimate and fraud transactions between January 1, 2019 to December 31, 2020. It covers credit cards of 1000 customers doing transactions with a pool of 800 merchants. The data consists of two data sets: `fraudTrain.csv` (what we worked on during our project time frame) and `fraudTest.csv` (ideally what we would use to further test our models).

* **Source**: [Link to the data set](https://www.kaggle.com/datasets/kartik2112/fraud-detection)
* **Details**: Features include transaction merchant, category, amount, and date/time. 

## Data Preprocessing
Data preprocessing involved transforming the raw data into a suitable format for machine learning:

- **Transaction Characteristics**: Log transformation for transaction amounts and extraction of timing features (transaction hour, day of week).
- **Cumulative Metrics**: Added transaction count and 7-day spending to track user activity.
- **Fraud Indicators**: Included fraud flag for recent fraud detection and used transaction frequency and spending velocity as fraud indicators.
- **Demographic Factors**: Used age and job type to analyze fraud patterns across demographics.
- **Distance and Location**: Calculated distances between cardholder's home and merchant locations, and between consecutive transactions, to detect location anomalies.
- **Data Cleaning & Balancing**: Handled missing values, outliers, and balanced the dataset using SMOTE for fraud class.

## Feature Engineering
Key features were engineered to improve model performance:
- **amt**: Log-transformed transaction amount to reduce skewness and normalize data.
- **city_pop**: Population of the transaction city, indicating possible location-based patterns.
- **transaction_hour**: Extracted from transaction timestamp to capture time-based patterns.
- **transaction_count**: Total transaction count for each cardholder, helping to detect abnormal spikes in activity.
- **age**: Cardholder's age, which may correlate with specific spending behaviors and fraud patterns.
- **trans_7d_count**: Number of transactions in the past 7 days, used to identify sudden activity increases.
- **prev_trans_count**: Previous transaction count to capture historical transaction behavior.
- **spending_velocity**: Rate of spending over time, used to identify sudden increases in spending.
- **distance**: Distance between consecutive transaction locations, detecting irregular travel patterns.
- **fraud_7d_flag**: A binary flag indicating fraud within the last 7 days, used to capture ongoing fraud patterns.

## Models Used
In this project, multiple machine learning models were evaluated to detect fraudulent transactions. Each model has its strengths in identifying complex patterns and outliers in data:
### 1. Logistic Regression
- **Purpose**: A linear model used for binary classification to predict whether a transaction is fraudulent (1) or legitimate (0).
- **Why Used**: Logistic Regression provides a baseline and is interpretable, making it useful for understanding feature importance.

### 2. Random Forest
- **Purpose**: An ensemble model that builds multiple decision trees and combines their predictions.
- **Why Used**: Random Forest is effective in handling complex datasets with interactions between features, and it is robust to overfitting.

### 3. XGBoost
- **Purpose**: A gradient boosting algorithm that builds an ensemble of decision trees sequentially, correcting errors made by previous trees.
- **Why Used**: XGBoost is highly efficient and has been proven to perform well in classification tasks, especially in handling imbalanced datasets.

### 4. Neural Networks
- **Purpose**: A deep learning model that consists of multiple layers of neurons to detect complex patterns in large datasets.
- **Why Used**: Neural Networks are ideal for capturing non-linear relationships in large and complex datasets like fraud detection.
  
### 5. Decision Tree
- **Purpose**: A non-linear classification algorithm that splits the data into subsets based on feature values, recursively creating a tree structure.
- **Why Used**: Decision Trees are simple, interpretable models that can handle both numerical and categorical features. They are particularly useful for identifying patterns in high-dimensional datasets.

## Installation
To use this project, follow these steps:

#### Prerequisites:
Make sure you have the following installed on your machine:
1. Python (version 3.6 or later)
2. Jupyter Notebook
3. pip (Python package installer)

#### Clone the Repository
Clone the repository using the following command:

```sh
git clone https://github.com/Anas10202/mastercard_fraud_detection.git
cd mastercard_fraud_detection
```

#### Install Dependencies
Manually install the necessary packages with the following command:

```sh
pip install jupyter pandas numpy scikit-learn matplotlib seaborn
```

## Usage
To launch the Jupyter Notebook interface, run the following command in your terminal:

```sh
jupyter notebook
```
This will open the Jupyter Notebook interface in your web browser.

### Opening the Notebook
Navigate to the directory where you cloned the repository and open the relevant `.ipynb` file. For example:

``` sh
cd path/to/your/notebook
jupyter notebook Mastercard1_CreditCardFraudDetection.ipynb
```

#### Running the Notebook
1. Cell Execution: Execute cells in the notebook sequentially. Run an individual cell by clicking it and typing `Shift + Enter`.
2. Modify Parameters: If desired, parameters and variables may be changed in their corresponding cells. Run the cell or the entire notebook to verify changes in the results.
3. View Results: As each notebook cell runs, outputs such as plots, tables and textual results will be displayed below each cell, unless purposely not displayed.

#### Saving the Notebook
Save work frequently by clicking the save icon or typing `Ctrl + S`.

#### Deactivating the Virtual Environment
When finished working, deactivate the virtual environment with:

 ``` sh
deactivate
```

## Contributing
We welcome contributions from the community to enhance and improve this project!

#### Getting Started
1. Fork the Repository: Click the "Fork" button at the top right of the repository page. This will create a copy of the repository in your GitHub account.
2. Clone the Repository: Clone the forked repository to your local machine using the following command:
``` sh
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```
3. Create a new branch for a new contribution using the following command:
``` sh
git checkout -b contribution/your-contribution
```

#### Making Changes
1. Ensure all libraries that are listed in the notebook are installed.
2. Make changes, but try to follow the existing style and conventions of the project.
3. Commit changes using a descriptive commit message:
``` sh
git add
git commit -m "Add contribution: your-contribution"
```

#### Submitting Changes
1. Push to the forked repository:
``` sh
git push origin contribution/your-contribution
```
2. Create a Pull Request: Open a pull request (PR) to the main repository. Include a clear title and description of your changes. Make sure to reference any related issues or PRs, if applicable.

#### Code Review:
If we receive contributions, we will try our best to respond with feedback or comments. Please make any necessary adjustments and commit them to your branch, if applicable.

Thank you for your contribution! Together, we can learn more together and make this project better!

## License
This project is licensed under the Apache 2.0 License - see the [LICENSE](https://github.com/Anas10202/mastercard_fraud_detection/blob/main/LICENSE) file for details.

## Credits and Acknowledgements
* **Team Members**: [Anas Ahmed](https://www.linkedin.com/in/anas-ahmed1/), [Ashley Nguyen](https://www.linkedin.com/ashleytlnguyen), Tarina Priti
* **Mastercard Challenge Advisors**: Vikas Bishnoi, Dhivya Jayaraman
* **Cornell Tech Course Support/TA**: Dev Ashar
___
* **Libraries**: NumPy, Pandas, Scikit-learn, Matplotlib, Seaborn, Keras, XGBoost
* **Applications**: Google Colab, Jira, Slack
* **Data Set Source**: Kaggle
