# Comparative Analysis of Anomaly Detection Algorithms on NAB Ambient Temperature Data

This project applies and compares multiple machine learning algorithms to detect anomalies in the **Numenta Anomaly Benchmark (NAB)** ambient temperature dataset. The objective was to evaluate the effectiveness of various anomaly detection techniques and identify anomalous temperature readings.

## Project Overview
In this project, we explore a variety of unsupervised and semi-supervised machine learning algorithms to detect anomalies in the time-series data of ambient temperature. Due to the absence of labeled data, performance was evaluated based on qualitative insights.

### Algorithms Used:
- **KMeans Clustering**: Used to detect anomalies based on distance from cluster centroids, effective for detecting anomalies at extreme values and sharp spikes in the data.
- **Isolation Forest**: A tree-based anomaly detection method that isolates observations to flag outliers, performed well on high-dimensional and complex data.
- **One-Class SVM**: A support vector machine method used to identify anomalies by creating a boundary around normal data points.
- **Elliptic Envelope**: Fit to the data under the assumption of a Gaussian distribution and flagged data points outside the envelope as anomalies.
- **Markov Chains**: Detected sequential anomalies based on transitions between states, which worked well for time-based anomalies.
- **LSTM (Long Short-Term Memory)**: A recurrent neural network (RNN) used to capture temporal dependencies and detect anomalies in time-series data.

## Key Findings:
- **KMeans**: Worked well for detecting extreme anomalies but was limited in handling temporal dependencies.
- **Isolation Forest**: Identified a wide range of anomalies effectively, handling complex data distributions without assumptions about the shape of clusters.
- **One-Class SVM**: Performed well for linear anomalies but required significant tuning for non-linear relationships.
- **Elliptic Envelope**: Detected anomalies effectively when the data followed a roughly Gaussian distribution but struggled with non-Gaussian distributions.
- **Markov Chains**: Captured temporal anomalies based on transitions between predefined states, suitable for time-based data.
- **LSTM**: The RNN captured sequential dependencies and detected temporal anomalies but required careful regularization to avoid overfitting.

## Methodology:
1. **Data Preprocessing**:
   - Converted time-series data to features such as hour of the day, day of the week, and daylight status.
   - Scaled the data using standardization for models sensitive to scale.
   
2. **Algorithm Implementation**:
   - Each algorithm was applied to the dataset and tuned to detect anomalies based on its underlying approach.
   - Due to the lack of labeled data, a qualitative analysis of the detected anomalies was performed.
   
3. **Results Analysis**:
   - Anomalies were visualized across different algorithms to compare their behavior and performance.
   - The results were interpreted based on the nature of the anomalies (e.g., sharp spikes, subtle deviations, sequential changes).

## Future Improvements:
- Incorporating a labeled dataset for more quantitative evaluation (e.g., precision, recall, F1 score).
- Exploring hybrid approaches that combine temporal and density-based anomaly detection techniques.
- Applying additional domain-specific features to enhance the accuracy of the anomaly detection.

