# Task G — Configure Pipeline Orchestration and Scheduling

## Objective
Design an orchestration framework to automate execution of the complete real estate data pipeline. The system manages scheduling, module dependencies, retries, and failure handling to ensure smooth and reliable data flow.

---

## Pipeline Stages Orchestrated

1. Data Ingestion
2. Data Cleaning & Standardization
3. Feature Engineering
4. Valuation Model Training
5. Prediction & Monitoring
6. Logging & QC

---

## Orchestration Architecture

### 1. Workflow Management
The pipeline is structured as sequential dependent tasks:

Ingestion → Cleaning → Feature Engineering → Model Training → Prediction → Logging

Each stage must complete successfully before the next begins.

---

### 2. Scheduling Strategy

- Daily automated runs for new data ingestion
- Weekly model retraining
- On-demand manual trigger option
- Scheduled monitoring reports

---

### 3. Dependency Management

- Cleaning depends on successful ingestion
- Feature engineering depends on cleaned data
- Model training depends on engineered features
- Prediction depends on trained model

Task dependencies are enforced to prevent incomplete execution.

---

### 4. Retry & Failure Handling

- Automatic retry up to 3 times for transient failures
- Logging of failure reason
- Alert triggered for critical failure
- Pipeline stops if critical stage fails

---

### 5. Execution Monitoring

- Track execution start and end time
- Measure stage-wise duration
- Record success/failure status
- Maintain run history log

---

## Tools (Conceptual)

Possible orchestration tools:
- Apache Airflow
- Prefect
- Cron-based scheduling
- Custom Python scheduler

(Design is tool-agnostic and adaptable.)

---

## Expected Outcome

- Fully automated pipeline execution
- Reduced manual intervention
- Reliable task dependency handling
- Scheduled and repeatable workflow management
