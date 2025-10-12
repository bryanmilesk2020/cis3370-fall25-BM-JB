# Project Plan
## Introduction
## Milestones
### Milestone 1: Project Setup & Dataset Preparation
Set up GitHub repo structure (docs/, src/, data/, notebooks/, etc.).
Download and organize UNB CIC-IDS-2018 dataset PCAP files.
Install and configure Zeek for traffic analysis.
Document project plan, scope, and backlog in GitHub Issues.

### Milestone 2: Zeek Log Extraction & Parsing
Run Zeek on PCAPs to extract ssl.log and conn.log.
Validate completeness and consistency of logs.
Write Python scripts to parse Zeek logs into structured format (CSV/JSON).
Initial exploration of TLS handshake metadata (cipher suites, certs, etc.).

### Milestone 3: Feature Engineering & Data Processing
Engineer key features:
Cipher suites offered
Certificate validity periods
Connection duration
Packet length statistics
Handle missing values and normalize feature sets.
Split dataset into training, validation, and test sets.

### Milestone 4: Model Training & Evaluation
Implement classifiers in Scikit-learn: Random Forest, Gradient Boosting.
Evaluate models with metrics: Accuracy, Precision, Recall, F1, ROC-AUC.
Tune hyperparameters and document results.
Select the best-performing model for deployment.

### Milestone 5: Integration with Elasticsearch
Install and configure Elasticsearch.
Ingest processed Zeek flow data.
Push model predictions into Elasticsearch indexes.
Verify indexing and querying performance.

### Milestone 6: Kibana Dashboard & Alerts
Set up Kibana to visualize traffic flow data and predictions.
Build dashboards: malicious vs benign traffic trends, TLS cipher suite usage, session statistics.
Configure alerting for sessions classified as malicious.
Finalize documentation of dashboard usage.

### Milestone 7: Testing, Documentation & Final Deliverables
Test pipeline end-to-end (PCAP → Zeek → Features → Model → Elasticsearch → Kibana).
Write user/deployment guide in repo (README.md, wiki).
Conduct peer review or demo presentation.


Prepare final project report and presentation slides.

