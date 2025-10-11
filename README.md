# 🧠 SmartNexxie – AI Smart Parking System

### 🚗 AI-Powered Parking Analytics, Blockchain Verification, RAG Assistant, and Power BI Integration

**SmartNexxie** is an **end-to-end intelligent parking management platform** that unifies **computer vision, IoT sensor streams, retrieval-augmented prediction (RAG), and blockchain verification** through **Microsoft Fabric’s Lakehouse** and **EventStream**.

This solution integrates **YOLOv8**, **PySpark**, **Vector Embeddings**, **MCP Governance**, and **Power BI Dashboards** for **real-time monitoring, AI-assisted predictions, and explainable analytics**.

---

## 🧩 PROJECT OVERVIEW

| Component                         | Description                                                                        |
| --------------------------------- | ---------------------------------------------------------------------------------- |
| **01_Complete_Setup_And_Data**    | Sets up Fabric Delta tables, ingests IoT data streams & synthetic traffic datasets |
| **02_AI_Processing_Predictions**  | Runs YOLO detection, AI inference, RAG embeddings, and blockchain verification     |
| **03_Monitoring_Dashboard**       | Monitors system health, KPIs, and real-time insights using EventStream & Spark     |
| **04_PowerBI_Advanced_Analytics** | Generates Power BI metrics, data marts, and predictive business insights           |
| **05_YOLOv8_Visualization**       | Visual AI demo for live parking video detection and RAG explanation assistant      |

---

## 🧱 SYSTEM ARCHITECTURE

```
                ┌───────────────────────────┐
                │  IoT Parking Sensors + CCTV│
                └────────────┬───────────────┘
                             │ (EventStream)
                             ▼
                 ┌───────────────────────────┐
                 │ Fabric Delta Lakehouse    │
                 └────────────┬───────────────┘
                             │
             ┌───────────────┴──────────────────┐
             │                                  │
             ▼                                  ▼
    ┌───────────────────────┐         ┌────────────────────────┐
    │ AI Processing (YOLOv8)│         │ Traffic Predictions RAG │
    └─────────────┬─────────┘         └──────────┬──────────────┘
                  │                              │
                  ▼                              ▼
        ┌──────────────────┐          ┌────────────────────────┐
        │ Blockchain Layer │          │ Model Context Protocol │
        └────────┬─────────┘          └────────┬───────────────┘
                 │                              │
                 ▼                              ▼
       ┌────────────────────────────────────────────────────────┐
       │ Power BI + Fabric Dashboards + Visual RAG Assistant     │
       └────────────────────────────────────────────────────────┘
```

---

## ⚙️ SETUP INSTRUCTIONS

### 1️⃣ Environment Setup

Install dependencies:

```bash
pip install pyspark pandas numpy ultralytics opencv-python faiss-cpu sentence-transformers
pip install matplotlib python-docx openpyxl reportlab
pip install watchdog websockets
```

If using **Microsoft Fabric or Synapse**:

* Attach your **Lakehouse (Delta)**.
* Enable **EventStream** and **Real-Time Hub**.
* Run notebooks in sequence (01 → 05).

---

## 📁 Folder Structure

```
SmartNexxie-AI-Smart-Parking/
│
├── data/
│   ├── parking_zones.json
│   ├── sample_video.mp4
│   └── mock_sensor_data.csv
│
├── models/
│   ├── yolov8n.pt
│   └── faiss_index.index
│
├── notebooks/
│   ├── 01_Complete_Setup_And_Data.html
│   ├── 02_AI_Processing_Predictions.html
│   ├── 03_Monitoring_Dashboard.html
│   ├── 04_PowerBI_Advanced_Analytics.html
│   └── 05_YOLOv8_Visualization.html
│
├── src/
│   ├── setup_and_data.py
│   ├── ai_processing_predictions.py
│   ├── monitoring_dashboard.py
│   ├── powerbi_advanced_analytics.py
│   ├── yolo_visualization.py
│   └── rag_assistant.py
│
└── README.md
```

---

## 🚀 MODULES OVERVIEW

### 🏗️ 01 — Data Setup (IoT + EventStream + Delta)

* Simulates **IoT sensors** + **CCTV feeds** using `watchdog` and `websockets`.
* Streams data to **Microsoft Fabric EventStream** and **OneLake Delta tables**.
* Creates:

  * `ParkingSensorData`
  * `TrafficCameraData`
  * `HistoricalTraffic`
  * `ModelRegistry`

**Technologies:**
`EventStream`, `Spark Structured Streaming`, `Delta Lake`, `Fabric Lakehouse`, `Python Watchdog`

---

### 🧠 02 — AI Processing (YOLO + Predictions + MCP + RAG)

* YOLOv8 for vehicle detection (`ultralytics`).
* **RAG (Retrieval-Augmented Generation)** for context-aware predictions.
* Embeddings built with `sentence-transformers (all-MiniLM-L6-v2)`.
* FAISS vector store for similarity search.
* **MCP (Model Context Protocol)** for AI governance & Hedera blockchain audit.
* Event-driven updates from **EventStream** → Model inference → Delta updates.

**Technologies:**
`YOLOv8`, `PyTorch`, `RAG`, `FAISS`, `Sentence-Transformers`, `PySpark`, `Hedera SDK (simulated)`, `EventStream`

---

### 📊 03 — Monitoring & Dashboard (Spark + Lakehouse + EventStream)

* Real-time KPIs on parking utilization and YOLO health.
* Stream analytics from EventStream to Spark DataFrames.
* Monitors:

  * Occupancy trends
  * Confidence drift
  * Blockchain verification stats
  * Event-based alerts

**Technologies:**
`PySpark SQL`, `Delta Live Tables`, `Microsoft Fabric EventStream`, `Kafka`, `WebSocket Dashboard`

---

### 📈 04 — Power BI Advanced Analytics

* Power BI marts for:

  * `RealTimeOccupancy`
  * `TrafficAnalytics`
  * `AIConfidenceMetrics`
  * `BlockchainAuditTrail`
* Custom DAX KPIs + RLS (Row-Level Security)
* Integration via `Power BI Streaming Datasets` API

**Technologies:**
`Power BI`, `Microsoft Fabric Dataflow`, `DAX`, `Lakehouse DirectQuery`, `Streaming Dataset API`

---

### 🎥 05 — YOLOv8 Visualization + RAG Assistant

* Computer vision dashboard showing:

  * Detected vehicles
  * Occupancy overlays
  * AI-predicted availability
* Integrated **RAG Assistant** that answers natural language queries like:

  > “Which zones are most congested between 8–10 AM on weekdays?”

**Technologies:**
`OpenCV`, `Matplotlib`, `Ultralytics YOLOv8`, `RAG (Sentence-Transformers + FAISS)`, `PySpark`, `Power BI`

---

## 🧠 SAMPLE RAG QUERY

```python
from rag_assistant import RAGAssistant

rag = RAGAssistant(spark)
rag.build_vector_store(["HistoricalTraffic"], force_rebuild=True)

query = "Which zones have the highest average occupancy during weekday mornings?"
result = rag.answer(query, top_k=5, mcp_system=mcp)

print("Answer:", result["answer"])
```

**Sample Output:**

```
Answer:
Zone_B and Zone_C have the highest weekday morning occupancy (avg 89% and 85%).

Retrieved docs:
- Zone_B 2025-06-02 score: 0.89
- Zone_C 2025-06-03 score: 0.87
```

---

## 🧰 TECHNOLOGY STACK

| Layer                        | Tools & Frameworks                                                         |
| ---------------------------- | -------------------------------------------------------------------------- |
| **Data Ingestion**           | Microsoft Fabric EventStream, Delta Lake, PySpark Streaming                |
| **AI/ML Models**             | YOLOv8, LSTM, Sentence-Transformers, FAISS, PyTorch, TensorFlow (optional) |
| **Governance & Security**    | Model Context Protocol (MCP), Hedera Blockchain (simulated), JSON Hashing  |
| **Analytics & BI**           | Power BI, Fabric Dataflows, Spark SQL, DAX                                 |
| **Visualization & Frontend** | OpenCV, Matplotlib, Power BI Embedded                                      |
| **Storage**                  | Microsoft OneLake, Delta Lakehouse, Parquet                                |
| **Orchestration**            | EventStream, Lakehouse Pipelines, Azure Functions (optional)               |
| **Language / Framework**     | Python 3.11, PySpark, Pandas, SQL                                          |

---

## ⚙️ KPIs & ALERTS

| Metric                  | Target | Action                     |
| ----------------------- | ------ | -------------------------- |
| Occupancy Rate          | <85%   | Notify Operations          |
| YOLO Confidence         | >0.9   | Continue Normal Ops        |
| Blockchain Verification | >95%   | Maintain Data Integrity    |
| RAG Retrieval Accuracy  | >0.88  | Adjust Embeddings if Lower |
| EventStream Latency     | <2 sec | Ensure Real-Time Flow      |

---

## 🧾 LICENSE

This project is licensed under the **MIT License**.

---

## 👤 AUTHOR

**Daniel Muthama**
💻 Software Engineer | AI & Data Science Specialist
🌍 Kenya, Africa | Remote-Ready
📧 [danielmuthama.dev@gmail.com](mailto:danielmuthama.dev@gmail.com)

---

## ⭐ FUTURE ROADMAP

* [ ] Deploy **Azure Containerized EventStream RAG System**
* [ ] Integrate **Live WebSocket Dashboard**
* [ ] Add **EV vs Non-EV Classification**
* [ ] Expand to **Smart City Traffic Flow Predictions**
* [ ] Build **LLM-based Parking Insights Assistant**

