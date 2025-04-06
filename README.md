# Time-Based Anomaly Detection in Credit Card Transactions

![screenshot-localhost_8888-2025 04 06-12_47_24](https://github.com/user-attachments/assets/607730db-9b95-4c4d-b0ab-29ebafb3107c)

### Project Overview

This project focuses on detecting fraudulent transactions by analyzing spending spikes within short time frames. Using a rolling sum approach, we identify unusual patterns in credit card transactions that may indicate fraud. The analysis includes:

- Time-based transaction sorting
- Rolling sum calculation for spending clusters
- Threshold-based anomaly detection (top 1% of transaction sums)
- Visualization of anomalies

### Dataset

The project uses the creditcard.csv dataset, which contains:

- Time: Transaction timestamp (converted to datetime)
- Amount: Transaction value
- V1-V28: Anonymized PCA-transformed features
- Class: Fraud label (0 = normal, 1 = fraud)

### Methodology

1. Data Preprocessing
- Normalize numerical features (excluding the fraud label).
- Convert Time to datetime and sort chronologically.

2. Anomaly Detection
- Compute a rolling sum of transaction amounts over a 5-transaction window.
- Flag anomalies where the rolling sum exceeds the 99th percentile threshold.

3. Visualization
- Plot rolling sums over time with anomalies highlighted in red.

### Results

- Detected anomalies represent unusually high spending clusters in a short time.
- These could indicate:
- Fraudulent transactions (e.g., card testing, rapid high-value purchases).
- Legitimate but unusual spending (e.g., bulk purchases).

### Future Enhancements

- Dynamic Thresholding: Adjust thresholds based on user spending history.
- Machine Learning Integration: Use LSTMs or autoencoders for adaptive anomaly detection.
- Real-Time Monitoring: Deploy as an API for live transaction screening.
- Multi-Feature Analysis: Combine with location, merchant category, and behavioral patterns.

### Conclusion

This project explored time-based anomaly detection in credit card transactions by analyzing sudden spending spikes within short time frames. By calculating a rolling sum of transaction amounts over a 5-transaction window and flagging values exceeding the 99th percentile threshold, I successfully identified unusual spending patterns that could indicate potential fraud or anomalous behavior.

### Source

[Synthetic Bank Transfers Dataset from Kaggle](https://www.kaggle.com/datasets/nyingsha/synthetic-bank-transfers)
