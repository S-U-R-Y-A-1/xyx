
# 🧠 ForecastIQ - Intelligent Resource Monitoring System

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Angular](https://img.shields.io/badge/Angular-17-red.svg)](https://angular.io/)
[![Prometheus](https://img.shields.io/badge/Prometheus-2.47-orange.svg)](https://prometheus.io/)
[![Docker](https://img.shields.io/badge/Docker-20.10+-blue)](https://www.docker.com/)

> ⚙️ A full-stack observability platform combining real-time monitoring with AI-powered forecasting for proactive IT resource optimization.

---

## 🌟 Features

- 🔄 **Real-time monitoring** of CPU, RAM, and disk via Prometheus exporters  
- 🚨 **Automated alerting** with customizable rules via Alertmanager  
- 🤖 **AI-driven forecasting** using Facebook Prophet for usage trends  
- 📊 **Modern dashboard** with Angular + Chart.js visualizations  
- 🐳 **Containerized deployment** with Docker Compose (K8s optional)

---

## 🛠️ Tech Stack

| Layer             | Technologies                              |
|------------------|-------------------------------------------|
| **Frontend**      | Angular 17, Chart.js                      |
| **Backend API**   | FastAPI (Python 3.9), Uvicorn             |
| **Monitoring**    | Prometheus, Node Exporter, Alertmanager  |
| **Forecasting**   | Facebook Prophet, Pandas, Matplotlib      |
| **Dashboarding**  | Grafana                                   |
| **Infrastructure**| Docker, (optional) Kubernetes HPA         |

---

## 🚀 Getting Started

### 🔧 Prerequisites

- Docker `20.10+`
- Python `3.9+`
- Node.js `18+` (for Angular development)

### 📦 Installation

```bash
# Clone the repo
git clone https://github.com/yourusername/resource-monitoring-system.git
cd resource-monitoring-system

# Launch the full stack
docker-compose up --build -d
````

### 🖥️ Access Services

* **Angular Dashboard**: [http://localhost:4200](http://localhost:4200)
* **Prometheus UI**: [http://localhost:9090](http://localhost:9090)
* **Grafana**: [http://localhost:3000](http://localhost:3000) (Login: `admin` / `admin`)
* **FastAPI Docs**: [http://localhost:8000/docs](http://localhost:8000/docs)

---

## 📊 AI Forecasting Workflow

1. **Export Metrics**
   Collect historical resource usage data:

   ```bash
   python python/backend.py
   ```

2. **Train Forecasting Model**
   Build and save Prophet model:

   ```bash
   python python/prometheus.py
   ```

3. **Serve Frontend** (if not using Docker):

   ```bash
   cd angular-frontend
   npm install
   ng serve
   ```

---

## 📁 Project Structure

```
.
├── angular-frontend/         # Angular UI app
├── python/          # FastAPI API with ML logic
├── prometheus/
│   └── alert-rules.yml
|   └── prometheus.yml          # Prometheus config + alert rules
├── docker/                  # ML scripts
│   ├── DockerFile
│   └── docker-compose.yml
└── README.md
```

---

## 📈 Sample Dashboard

1. CPU Usage
   
---![CPU Usage limit](https://github.com/user-attachments/assets/5eb315b5-523f-484e-85d6-6fbc80b03cbe)

2. CPU, Memory, Network Stat

---![CPU, Memory, Network Stat](https://github.com/user-attachments/assets/a1af0d79-e3c0-4ecf-972a-bfb4bd45d351)

3. Forecasted CPU Usage

---![Forecasted CPU Usage](https://github.com/user-attachments/assets/ca98245c-e78f-49db-aa92-f56c269abae8)


## ⚠️ Alerting Rules

Triggers alerts when:

* 🔥 CPU usage > 80% for 5 minutes
* 🧠 Memory usage > 90%
* 💾 Disk space < 10% free

Configured via **Prometheus Alertmanager**.

---

## 🤖 ML Implementation

```python
# AI Forecasting with Prophet
from prophet import Prophet

model = Prophet(seasonality_mode='multiplicative')
model.fit(training_data)

future = model.make_future_dataframe(periods=24, freq='H')
forecast = model.predict(future)
```

* Forecasts 24 hours into the future
* Supports weekly and daily seasonality
* Results are visualized via Angular charts


---

## 🙋‍♂️ Maintainer

Developed by [Surya](https://github.com/S-U-R-Y-A-1)
Integrated MSc AIML @ Coimbatore Institute of Technology

---

## 🔮 Future Scope

* Integrate anomaly detection (e.g., Isolation Forest)
* Add multi-node Kubernetes cluster support
* Use LSTM for long-term trend forecasting

---

## 📫 Feedback & Contributions

Have ideas or suggestions?
Open an issue or submit a PR — contributions are welcome!

⭐ **Star the repo** if this project helped you!

