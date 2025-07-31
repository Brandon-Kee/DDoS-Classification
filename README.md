# DDoS Classification
This project focuses on detecting Distributed Denial-of-Service (DDoS) attacks by working with labeled network traffic data. It includes steps for preprocessing the data, visualizing patterns and anomalies, and training a Random Forest Classifier to identify malicious activity. The goal is to build an effective and interpretable model for distinguishing between normal and attack traffic.

## DDoS Attacks
A Distributed Denial-of-Service (DDoS) attack is a cyberattack where multiple compromised devices flood a target system, such as a website or server, with excessive traffic to overwhelm its resources and disrupt normal service. These attacks can cause downtime, slow performance, and loss of access for legitimate users. DDoS attacks are often used to extort, distract, or damage organizations by making their online services unavailable.

## The Data
The data for this project was sourced from the [Network Intrusion Dataset](https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset) on Kaggle.

Data preprocessing included: 
- Removing missing values 
- Stripping whitespace from column names
- Mapping `Label` to binary values (BENIGN → 0, DDoS → 1)
- Visualizing missing values with bar plots

## Model Training
The **Random Forest model** was used in this project because it is highly effective for **binary classification tasks with many numerical features**, like DDoS detection. Our dataset contained 78 flow-level metrics, and Random Forest can naturally handle **high-dimensional data** without the need for feature scaling or extensive preprocessing. It is also **robust to noise and outliers**, which is critical for network traffic data that can be irregular or bursty. Additionally, Random Forest **captures non-linear relationships** between features, allowing it to distinguish subtle patterns that separate benign flows from DDoS attacks. Another reason for using Random Forest is its ability to **provide feature importance scores**, helping us understand which network characteristics contribute most to detecting attacks. Overall, it was chosen because it offers **high accuracy, strong generalization, and interpretability** with minimal tuning, making it well-suited for this DDoS classification task.

## Results
The results of the DDoS classification model demonstrate near-perfect performance, with an overall accuracy of 99.99% and equally strong precision, recall, and F1-scores for both benign and DDoS traffic. The confusion matrix highlights that almost all benign flows were correctly identified as benign, and nearly all DDoS flows were correctly flagged as attacks, with only a handful of misclassifications in each direction. In practical terms, this means the model can reliably detect malicious traffic with minimal false alarms and virtually no missed attacks, making it highly effective for network defense scenarios where both sensitivity and precision are critical.

### Confusion Matrix
<img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/f420b602-0f88-484d-8242-8e4ab446f8e8" />

## Next Steps

- **Experiment with temporal validation**  
  Simulate real-time detection using sliding windows to evaluate performance on time-based splits.

- **Implement streaming inference**  
  Deploy the model to process live network traffic for near real-time DDoS detection.

- **Extend to multi-class classification**  
  Classify specific DDoS attack types rather than just binary benign/attack labeling.

- **Optimize for deployment**  
  Explore hyperparameter tuning and model compression for faster inference in production environments.
