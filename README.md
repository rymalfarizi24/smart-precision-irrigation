# 🌱 Autoencoder-Based Fault Detection & Diagnosis for Smart Precision Irrigation

![Dynamic JSON Badge](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2FLetsgobois24%2Fsmart-irrigation-precision%2Fmain%2Flaravel%2Fcomposer.json&query=require.laravel%2Fframework&logo=laravel&logoColor=%23FF2D20&label=Laravel&color=%23FF2D20)
![Dynamic JSON Badge](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2FLetsgobois24%2Fsmart-irrigation-precision%2Fmain%2Flaravel%2Fcomposer.json&query=require.livewire%2Flivewire&logo=livewire&logoColor=%234E56A6&label=Livewire&color=%234E56A6)
![Static Badge](https://img.shields.io/badge/%5E0.135-build?logo=fastapi&logoColor=%23009688&label=FastAPI&color=%23009688)
![Static Badge](https://img.shields.io/badge/%5E3.14-build?logo=keras&logoColor=%23D00000&label=Keras&color=%23D00000)
![Static Badge](https://img.shields.io/badge/3.8.0--core-build?logo=influxdb&logoColor=%2322ADF6&label=InfluxDB&color=%2322ADF6)
![Static Badge](https://img.shields.io/badge/10.4.32-build?logo=mariadb&logoColor=%23003545&label=MariaDB&color=%23003545)
![Static Badge](https://img.shields.io/badge/29.4.2-build?logo=docker&logoColor=%232496ED&label=Docker&color=%232496ED)







An end-to-end **IoT-enabled Smart Precision Irrigation** system featuring an **Autoencoder-based Fault Detection and Diagnosis (FDD)** framework for avocado cultivation. This project integrates embedded systems, machine learning, and a modern web platform to detect irrigation anomalies, diagnose potential faults, and provide real-time monitoring and notifications.

---

## 📖 Overview

Smart irrigation systems rely on sensor data and automated control to optimize water usage. However, failures such as sensor malfunction, irrigation blockage, valve failure, or abnormal watering behavior can reduce system reliability.

This project addresses these challenges by implementing an **Autoencoder-based Fault Detection and Diagnosis (FDD)** framework capable of detecting anomalous irrigation events and identifying the most probable fault using a knowledge-based diagnosis approach.

The complete system includes IoT devices, a backend service, databases, machine learning inference, and a web dashboard for monitoring and system management.

---

## ✨ Features

- 🌱 IoT-enabled smart precision irrigation
- 🤖 Autoencoder-based anomaly detection
- 🔍 Knowledge-based fault diagnosis
- 📡 Real-time communication using MQTT
- 📊 Interactive monitoring dashboard
- 🔔 Real-time fault notifications
- 📈 Historical irrigation event visualization
- 🐳 Dockerized deployment
- ⚡ REST API powered by FastAPI

---

## 🏗️ System Architecture
<p align="center">
  <img height="600" alt="image" src="https://github.com/user-attachments/assets/3f9b7954-1e86-4b75-92f3-5af7d2a9802b" />
</p>

---

## 🔧 Hardware Implementation

The physical implementation consists of ESP32-based IoT nodes, soil moisture sensors, solenoid valves, pumps, and supporting electrical components for automated irrigation and real-time data acquisition.

<table border="0">
  <tr>
    <td width="33%" valign="middle">
      <img src="https://github.com/user-attachments/assets/dbd34e2a-b8d5-4465-a89b-813bb50a049b" width="100%" />
    </td>
    <td width="33%" valign="middle">
      <img src="https://github.com/user-attachments/assets/cf581af7-5a07-44f0-8800-df122bb59d08" width="100%" />
    </td>
    <td width="33%" valign="middle">
      <img src="https://github.com/user-attachments/assets/42963819-3432-49f6-839c-a7114cfe8e06" width="100%" />
    </td>
  </tr>
</table>

<p align="center">
  <em>Physical implementation of the IoT-enabled smart precision irrigation system.</em>
</p>

---

## ⚙️ Workflow

1. ESP32 devices collect irrigation event data.
2. Sensor data are published to the MQTT broker.
3. FastAPI subscribes to MQTT topics and processes incoming data.
4. The Autoencoder reconstructs the input features.
5. Reconstruction error (MSE) is compared against a predefined threshold.
6. If an anomaly is detected, the dominant feature is identified.
7. A knowledge base maps the dominant feature to the most probable fault.
8. Detection results are stored in MariaDB.
9. The Laravel dashboard displays monitoring data, fault history, and real-time notifications.

---

## 🛠️ Tech Stack

### Embedded & Communication

- ESP32
- MQTT

### Backend

- FastAPI
- Python
- TensorFlow / Keras

### Database

- InfluxDB
- MariaDB

### Frontend

- Laravel
- Livewire
- Tailwind CSS
- ApexCharts

### Deployment

- Docker
- Docker Compose
- Nginx

---

## 🧠 Inference Pipeline

This repository performs **fault detection and diagnosis using a pre-trained Autoencoder model**. The backend receives irrigation event data, performs anomaly detection through reconstruction error analysis, and diagnoses detected anomalies using a knowledge-based fault mapping.

### Model

- Pre-trained Autoencoder Neural Network

### Input Features

- Moisture Before Irrigation
- Moisture After Irrigation
- Irrigation Duration
- Moisture Gain
- Moisture Rate

### Detection

- Reconstruction Error (Mean Squared Error)
- Threshold-based anomaly detection

### Diagnosis

- Knowledge-based fault mapping

> **Note**
>
> The complete model development process—including dataset preparation, preprocessing, feature engineering, hyperparameter tuning, training, and evaluation—is available in the **Model Training** repository.

## 🚨 Supported Fault Scenarios

The diagnosis module supports detection of several irrigation-related faults, including:

- Sensor Drift
- Sensor Freeze
- Under Irrigation
- Over Irrigation
- Incorrect Fuzzy Rule Base
- Incorrect Membership Function
- Clogged Nozzle
- Low Water Pressure
- Pipe Leakage
- Pipe Blockage

---

## 📈 Model Performance

| Metric | Score |
|--------|-------:|
| Accuracy | **97.50%** |
| Precision | **95.24%** |
| Recall | **100.00%** |
| F1-Score | **97.56%** |

---

## 🔗 Related Repository

The Autoencoder model used in this project is pre-trained. The complete machine learning pipeline is available in a separate repository:

- **Model Training:** https://github.com/Letsgobois24/smart-precision-irrigation-model.git

---

## 📂 Project Structure

```text
.
smart-irrigation-precision
│
├── fastapi/
│   │
│   ├── database/
│   │   ├── influxdb/
│   │   └── mariadb/
│   │
│   ├── model/
│   │   ├── best_model.keras
│   │   ├── scaler.pkl
│   │   └── prediction.py
│   │
│   ├── schema/
│   ├── services/
│   │
│   ├── app.py
│   ├── requirements.txt
│   ├── .env
│   ├── .env.production
│   └── Dockerfile
│
├── laravel/
│   │
│   ├── app/
│   ├── resources/
│   ├── routes/
│   │   └── web.php
│   ├── database/
│   ├── public/
│   ├── .env
│   ├── .env.production
│   └── Dockerfile
│
├── .env
├── docker-compose.yml
├── nginx.conf
└── README.md

```

---

## 🚀 Getting Started

### Prerequisites

- Docker
- Docker Compose
- Python 3.13+
- PHP 8.2+
- Composer

### Clone Repository

```bash
git clone https://github.com/Letsgobois24/smart-irrigation-precision.git
smart-irrigation-precision
```

### Run with Docker

```bash
docker compose up -d
```

---
## 📸 Web Dashboard

The web-based dashboard provides real-time monitoring of irrigation activities, system conditions, historical data, and fault detection results.

<p align="center">
  <img width="1366" height="768" alt="Web Dashboard" src="https://github.com/user-attachments/assets/8dd07a75-1281-4633-b352-3b1ee39bc2da" />
</p>

---

## 🔔 Fault Notification

When an anomaly is detected, the Fault Detection and Diagnosis (FDD) subsystem identifies the potential fault and displays a notification through the web dashboard.

<p align="center">
  <img src="https://github.com/user-attachments/assets/62308c57-6068-4a67-b52c-c9e052c16452" width="60%" alt="Fault Notification Modal" />
</p>

<p align="center">
  <em>Fault notification generated by the Fault Detection and Diagnosis subsystem.</em>
</p>

---

## 📚 Research

This repository was developed as part of an undergraduate thesis on an Autoencoder-based Fault Detection and Diagnosis framework for an IoT-enabled Smart Precision Irrigation system for avocado cultivation.

---

## 📄 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

**Rayhan Muhammad Alfarizi**

Electrical Engineering Graduate
Diponegoro University

LinkedIn: https://www.linkedin.com/in/rayhan-m-alfarizi/

GitHub: https://github.com/Letsgobois24
