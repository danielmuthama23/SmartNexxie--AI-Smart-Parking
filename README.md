
* Data setup
* AI Processing (YOLO + Predictions)
* Monitoring & Dashboard (Spark + Lakehouse)
* Power BI Integration
* Visual AI Demo (YOLOv8 Parking Visualization)

# 🧠 REIMAGE-AI SMART PARKING SYSTEM

### 🚗 AI-Powered Parking Analytics, Blockchain Verification, and Power BI Integration

Reimage-AI Smart Parking is an **end-to-end intelligent parking management system** that uses **computer vision, IoT sensor data, AI predictions, and blockchain validation** to optimize urban parking efficiency.

This system is built for **Microsoft Fabric Lakehouse** and integrates **YOLOv8**, **Spark SQL**, and **Power BI dashboards** for real-time monitoring and business intelligence.

---

## 🧩 PROJECT OVERVIEW

| Component                         | Description                                                             |
| --------------------------------- | ----------------------------------------------------------------------- |
| **01_Complete_Setup_And_Data**    | Sets up initial Lakehouse tables, simulates IoT sensor and traffic data |
| **02_AI_Processing_Predictions**  | Runs YOLO detection, model inference, and predictive analytics          |
| **03_Monitoring_Dashboard**       | Displays real-time data analytics and health monitoring                 |
| **04_PowerBI_Advanced_Analytics** | Generates Power BI metrics, data marts, and business KPIs               |
| **05_YOLOv8_Visualization**       | Visual computer vision demo – detects parking occupancy live from video |

---

## 🧱 SYSTEM ARCHITECTURE

```
                ┌──────────────────────────┐
                │   Parking Sensors (IoT)  │
                └────────────┬─────────────┘
                             │
                             ▼
                 ┌──────────────────────────┐
                 │   Fabric Delta Lakehouse │
                 └────────────┬─────────────┘
                             │
             ┌───────────────┴────────────────┐
             │                                │
             ▼                                ▼
    ┌───────────────────────┐        ┌────────────────────────┐
    │ AI Processing (YOLOv8)│        │ Traffic Predictions AI │
    └─────────────┬─────────┘        └──────────┬─────────────┘
                  │                             │
                  ▼                             ▼
        ┌──────────────────┐          ┌────────────────────────┐
        │ Blockchain Layer │          │ Model Context Protocol │
        └────────┬─────────┘          └────────┬───────────────┘
                 │                             │
                 ▼                             ▼
         ┌────────────────────────────────────────────────┐
         │ Power BI + Fabric Dashboards & Visualizations  │
         └────────────────────────────────────────────────┘
```

---

## ⚙️ SETUP INSTRUCTIONS

### 1️⃣ Environment Setup

Install the following (preferably in a virtual environment):

```bash
pip install pyspark pandas numpy ultralytics opencv-python
pip install matplotlib python-docx openpyxl reportlab
```

If using **Microsoft Fabric / Synapse**:

* Attach the **Delta Lakehouse** before executing notebooks.
* Run notebooks in sequence.

---

### 2️⃣ Folder Structure

```
reimage-ai-smart-parking/
│
├── data/
│   ├── sample_video.mp4
│   ├── parking_zones.json
│   └── mock_sensor_data.csv
│
├── models/
│   └── yolov8n.pt
│
├── notebooks/
│   ├── 01_Complete_Setup_And_Data.html
│   ├── 02_AI_Processing_Predictions.html
│   ├── 03_Monitoring_Dashboard.html
│   └── 04_PowerBI_Advanced_Analytics.html
│
├── output/
│   ├── powerbi_metrics.delta
│   ├── dashboard_summary.txt
│   └── parking_visual.mp4
│
├── src/
│   ├── setup_and_data.py
│   ├── ai_processing_predictions.py
│   ├── monitoring_dashboard.py
│   ├── powerbi_advanced_analytics.py
│   └── yolo_visualization.py
│
└── README.md
```

---

## 🚀 USAGE GUIDE

### STEP 1: Setup and Data Initialization

Run:

```python
python src/setup_and_data.py
```

This script creates:

* **ParkingSensorData**
* **TrafficCameraData**
* **HistoricalTraffic**
* **YOLOProcessedData**
* **TrafficPredictions**

All stored in your **Lakehouse**.

---

### STEP 2: AI Processing and Predictions

Run:

```python
python src/ai_processing_predictions.py
```

Performs:

* YOLO-based vehicle detection.
* AI inference for future parking occupancy.
* Blockchain-like verification simulation.
* Model Context Protocol (MCP) audit logging.

---

### STEP 3: Monitoring Dashboard

Run:

```python
python src/monitoring_dashboard.py
```

Displays:

* Occupancy rates by zone.
* Traffic congestion trends.
* YOLO performance metrics.
* Prediction accuracy.
* System health and freshness checks.

✅ Output Example:

```
🏥 SYSTEM HEALTH CHECK:
   Parking Data: ✅ HEALTHY
   Traffic Data: ✅ HEALTHY
   Predictions: ✅ HEALTHY
   YOLO Processing: ✅ HEALTHY
```

---

### STEP 4: Power BI Advanced Analytics

Run:

```python
python src/powerbi_advanced_analytics.py
```

Generates:

* Power BI optimized tables:

  * `PowerBI_RealTimeOccupancy`
  * `PowerBI_TrafficAnalytics`
  * `PowerBI_AIPerformance`
  * `PowerBI_BlockchainAudit`
* Advanced metrics and KPIs
* Business impact dashboards
* Alerts and AI insights

✅ Sample KPIs:

* Occupancy > 85% → Alert: “High Occupancy”
* Blockchain Verification < 90% → Alert: “Integrity Issue”

---

### STEP 5: YOLOv8 Parking Visualization

Run:

```python
python src/yolo_visualization.py
```

Displays and records visual parking occupancy analytics from video feed.

🧠 Features:

* Draws parking regions and tracks vehicles in real-time.
* Calculates **occupancy rate**, **availability**, and **confidence**.
* Saves annotated video (`output/parking_visual.mp4`).
* Integrates metrics with Power BI if desired.

---

## 🧠 SAMPLE OUTPUT

```
🎥 STEP 4: VISUAL AI DEMO – YOLOv8 PARKING MANAGEMENT VISUALIZATION
🚗 Processing video frames for parking visualization...
✅ Visualization complete — saved to output/parking_visual.mp4
🖼️ Processed 480 frames in 32s
📊 Final Occupancy Rate: 67.5% (9/12 occupied)
```

---

## 📊 POWER BI DASHBOARD SUMMARY

| Metric                     | Description                                     |
| -------------------------- | ----------------------------------------------- |
| **Real-Time Occupancy**    | Tracks zone occupancy using YOLO detections     |
| **Traffic Flow**           | Displays congestion levels and vehicle density  |
| **AI Performance**         | Shows YOLO and prediction system confidence     |
| **Blockchain Audit Trail** | Validates all IoT and AI data transactions      |
| **Business KPIs**          | Calculates revenue, utilization, and efficiency |

---

## 🔗 INTEGRATIONS

| Integration                            | Purpose                                 |
| -------------------------------------- | --------------------------------------- |
| **Microsoft Fabric / Delta Lakehouse** | Real-time analytics and data storage    |
| **Ultralytics YOLOv8**                 | Vehicle detection and tracking          |
| **Power BI**                           | Visualization and business intelligence |
| **MCP (Model Context Protocol)**       | AI model governance and traceability    |
| **Hedera Blockchain (Simulated)**      | Data immutability and audit logging     |

---

## 🧰 TECHNOLOGY STACK

| Layer                      | Tools Used                             |
| -------------------------- | -------------------------------------- |
| **Frontend Visualization** | Power BI, Matplotlib, OpenCV           |
| **AI/ML Models**           | YOLOv8, TensorFlow (optional), PyTorch |
| **Backend Processing**     | PySpark, Pandas, Microsoft Fabric      |
| **Storage**                | Delta Lakehouse (OneLake)              |
| **Security**               | Blockchain Verification (Simulated)    |
| **Governance**             | Model Context Protocol (MCP)           |

---

## 📈 KPIs AND ALERTS

| KPI                     | Target | Action                     |
| ----------------------- | ------ | -------------------------- |
| Occupancy Rate          | < 85%  | Notify operations          |
| AI Confidence           | > 0.9  | Continue normal operations |
| Blockchain Verification | > 95%  | Maintain ledger            |
| System Uptime           | > 99%  | SLA Compliance             |

---

## 🧠 ADVANCED INSIGHTS

✅ **Peak Hours:** 8:00 AM - 10:00 AM
✅ **Most Occupied Zone:** PZ-3 (92% average occupancy)
✅ **Blockchain Verified Records:** 99.2%
✅ **AI Confidence:** 91.1% across 12 cameras

---

## 🧾 LICENSE

This project is open-source and licensed under the **MIT License**.

---

## 👤 AUTHOR

**Daniel Muthama**
💻 Software Engineer | AI & Data Science Specialist
🌍 Kenya, Africa | Remote-friendly
📧 [danielmuthama.dev@gmail.com](mailto:danielmuthama.dev@gmail.com)

---

## ⭐ FUTURE ROADMAP

* [ ] Integrate **live streaming** dashboard via WebSocket
* [ ] Deploy **containerized version** using Docker + Azure Fabric
* [ ] Integrate **Power BI Streaming Dataset API**
* [ ] Add **vehicle classification (EV vs Non-EV)**
* [ ] Predict **future parking availability** by zone using LSTM

# SmartNexxie--AI-Smart-Parking
