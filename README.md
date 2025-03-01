# Anomaly Detection in Merchant Commission Transaction Data


This project focuses on identifying anomalous transactions within a dataset of merchant commissions of a crypto trading startup. Several methods are employed for anomaly detection, including statistical methods (Z-score), and machine learning techniques (Isolation Forest and Local Outlier Factor).

## Data

The project uses a dataset containing transaction information, including:

*   `merchantId`: Unique identifier for each merchant
*   `commissionAmount`: The commission amount for each transaction
*   `createdAt`: Timestamp of the transaction
*   `dob`: Date of birth of each merchant

## Methods

Three primary anomaly detection techniques:

1.  **Z-score:**  Identifies anomalies based on the number of standard deviations a transaction's commission amount deviates from the mean commission amount for a particular merchant. Different threshold values to balance sensitivity and specificity are experimented.

2.  **Isolation Forest:** An unsupervised learning method that isolates anomalies based on the idea that anomalies are few and different. The `contamination` parameter to control the expected proportion of anomalies is adjusted.

3.  **Local Outlier Factor (LOF):**  An unsupervised learning method that identifies anomalies based on local density variations. The number of neighbors (`n_neighbors`) and the expected contamination ratio (`contamination`) are crucial parameters.

The frequency of transactions, time of transactions ared also explored and all the results are combined to get better results.

## Evaluation

Since the dataset is unlabled, the models are evaluated using the following approaches:

1.  **Visual Inspection:** Examination of anomaly flags alongside the original data to identify visual patterns.

2.  **Parameter Sensitivity Analysis:** Testing various parameter settings to assess robustness.

3.  **Method Comparison:** Comparing anomaly flags across different methods to gain confidence in findings.

## Results

Each method and combination of methods yields a set of anomalies. Visual inspection and sensitivity analysis help interpret and tune the results. The final anomaly detection result is based on a combination of Z-score, Isolation Forest, LOF, transaction frequency, and transaction times, resulting in an anomaly rate of 27%.

## Usage

This code demonstrates the following steps:
1. Load the dataset.
2. Perform data analysis and visualization.
3. Apply different anomaly detection methods.
4. Evaluate the performance of each method by visualizing the results and comparing methods.

To reproduce the analysis, replace the placeholder data with your dataset and adapt the code based on the specifications of your dataset.

## Dependencies

*   pandas
*   pandasql
*   plotly
*   scipy
*   scikit-learn
*   matplotlib
