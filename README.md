Encrypted Traffic Analysis for Malware Detection

Overview

This project implements a machine-learning pipeline to classify encrypted network traffic as benign or malicious without decrypting packet payloads. The system relies on metadata extracted from TLS handshakes and connection-level statistics to detect suspicious behavior in encrypted sessions. 

Problem Statement

Modern network traffic is largely encrypted, limiting the effectiveness of traditional intrusion detection systems that rely on payload inspection. This project demonstrates how encrypted traffic can be analyzed using flow-level metadata and statistical features to identify potentially malicious activity.

Dataset

- UNB CIC-IDS-2018 dataset
- Contains realistic benign and malicious traffic
- Includes extensive TLS/SSL-encrypted sessions
- PCAP files processed using Zeek

Tools and Technologies

- Zeek for network traffic analysis and log generation
- Python for data processing and feature engineering
- Pandas and NumPy for data manipulation
- Scikit-learn for machine learning
- Elasticsearch for data indexing and storage
- Kibana for visualization and dashboards
- Docker and Docker Compose for Elastic Stack deployment

Data Extraction

- Zeek is used to process PCAP files
- Primary logs used:
- conn.log for connection metadata
- ssl.log for TLS session metadata
- Logs are merged at the session level
- No packet payloads are decrypted or inspected

Feature Engineering

- Connection duration
- Origin and response byte counts
- Total bytes per session
- Byte ratio between endpoints
- Packet rate and byte rate features
- TLS version indicators
- TLS session resumption flag

Machine Learning Pipeline

- Binary classification: benign (0) vs malicious (1)
- Random Forest classifier
- Features selected dynamically based on availability
- Model outputs:
- Hard prediction (rf_pred)
- Probability score of maliciousness (rf_score)
- Model trained and evaluated using train-test split

Output Data

Final dataset exported as CSV
Includes:
- Original flow metadat
- Engineered features
- Ground-truth or heuristic labels
- Machine learning predictions
- Model confidence scores
- CSV is ingested into Elasticsearch for visualization

Kibana Dashboard

- Distribution of benign vs malicious traffic
- Malicious traffic over time
- Top source and destination IPs associated with malicious sessions
- Model confidence score distributions
- Protocol and TLS version breakdowns

Interpretation of Labels

- is_malicious = 0 indicates benign traffic
- is_malicious = 1 indicates malicious traffic
- rf_score represents the model’s confidence that a session is malicious
- rf_pred is the final binary decision from the model

Limitations

- Does not decrypt or inspect payloads
- Does not identify specific malware families or attack types
- Heuristic labeling may introduce bias
- Intended as a behavioral detection and analytics system

Future Work

- Integrate true attack labels from CIC-IDS metadata
- Add TLS fingerprinting features such as JA3
- Improve real-time ingestion and alerting
- Extend classification to multi-class attack detection

Conclusion

This project demonstrates that encrypted traffic can be effectively analyzed using metadata-driven machine learning techniques. By combining Zeek, Python, and the Elastic Stack, the system provides a scalable and practical approach to encrypted traffic monitoring and threat detection.
