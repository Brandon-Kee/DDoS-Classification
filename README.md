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

## Results
The results of the DDoS classification model demonstrate near-perfect performance, with an overall accuracy of 99.99% and equally strong precision, recall, and F1-scores for both benign and DDoS traffic. The confusion matrix highlights that almost all benign flows were correctly identified as benign, and nearly all DDoS flows were correctly flagged as attacks, with only a handful of misclassifications in each direction. In practical terms, this means the model can reliably detect malicious traffic with minimal false alarms and virtually no missed attacks, making it highly effective for network defense scenarios where both sensitivity and precision are critical.

### Confusion Matrix
<img width="692" height="553" alt="image" src="https://github.com/user-attachments/assets/f420b602-0f88-484d-8242-8e4ab446f8e8" />

