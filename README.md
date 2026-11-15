# QueryLeaf – Smart Energy-Aware IoT API Gateway

An energy-aware multi-tier IoT API gateway that intelligently routes database queries across **Redis RAM Cache**, **Edge MongoDB**, and a **Cloud Data Warehouse** based on real-time latency, energy consumption, and data freshness constraints.

---

## Overview

Modern IoT applications generate high-dimensional, real-time telemetry streams from domains such as smart cities, healthcare, transportation, and industrial automation. Traditional static query heuristics struggle to handle the dynamic and non-linear nature of IoT workloads, often resulting in suboptimal query execution plans, high latency, and excessive energy overhead.

**QueryLeaf** addresses these bottlenecks by dynamically evaluating incoming requests and routing them to the optimal storage tier—balancing response speed, data freshness, and carbon/energy efficiency.

---

## Key Features

- **Adaptive Multi-Tier Query Routing:** Dynamically dispatches database queries across RAM Cache, Edge, and Cloud storage layers based on workload constraints.
- **Caching & Persistence:** Integrates **Redis** for low-latency in-memory lookups and **MongoDB** for structured edge storage.
- **Real-Time IoT Telemetry Monitoring:** Live tracking of incoming sensor query loads, throughput, and system health.
- **Energy & Carbon Footprint Analytics:** Evaluates query execution efficiency and resource overhead to promote sustainable data management.
- **Interactive Query Explorer & Benchmarking:** Built-in tools to test routing policies, inspect execution paths, and benchmark tier performance.

---

## Tech Stack

- **API & Backend:** FastAPI, Express.js
- **Storage & Caching:** Redis, MongoDB, Cloud Data Warehouse
- **Architecture:** Edge-Cloud Computing, RESTful API Development

---

## System Architecture

```text
[ IoT Devices / Sensors ]
           │
           ▼
┌─────────────────────┐
│  QueryLeaf Gateway  │ ──► Evaluates Latency, Freshness & Energy Constraints
└──────────┬──────────┘
           │
     ┌─────┴─────┬─────────────────┐
     ▼           ▼                 ▼
[ Redis ]   [ MongoDB ]   [ Cloud Warehouse ]
(RAM Cache) (Edge Tier)     (Cold/Analytics)
```

1. **Data Ingestion & Preprocessing:** Cleans and standardizes incoming IoT sensor payloads for efficient query parsing.
2. **Adaptive Routing Engine:** Evaluates query freshness, latency thresholds, and energy budgets to choose between cache, edge, or cloud execution.
3. **Monitoring & Telemetry Layer:** Continuously tracks response latency, throughput, and estimated carbon footprint across queries.

---

## Getting Started

### Prerequisites

- Python 3.9+
- Node.js 18+
- Running instances of Redis and MongoDB

### Installation

1. **Clone the repository**
   ```bash
   git clone [https://github.com/Shrushtipatil/queryleaf-iot-gateway.git](https://github.com/Shrushtipatil/queryleaf-iot-gateway.git)
   cd queryleaf-iot-gateway
   ```

2. **Install dependencies**
   ```bash
   # Install FastAPI service dependencies
   pip install -r requirements.txt

   # Install Express.js gateway dependencies
   npm install
   ```

3. **Configure environment variables**
   Create a `.env` file in the root directory:
   ```env
   REDIS_URL=redis://localhost:6379
   MONGO_URI=mongodb://localhost:27017/queryleaf
   CLOUD_DB_URI=<your-cloud-warehouse-uri>
   PORT=8000
   ```

4. **Start the services**
   ```bash
   # Run FastAPI service
   uvicorn main:app --reload

   # Run Express.js service
   npm start
   ```

---

## Research Context & Motivation

This project builds upon principles of energy-efficient IoT database query optimization and edge-cloud orchestration. As highlighted in recent literature (*Xiaowen Ma, PLOS ONE, 2024*), decoupling lightweight real-time query routing at the edge from heavier analytical workloads significantly reduces query response latency, memory footprint, and overall energy consumption in high-frequency IoT environments.

### Target Application Domains
- **Smart Cities & Intelligent Transportation:** Low-latency spatial-temporal queries for traffic automation and public infrastructure.
- **Industrial IoT & Smart Manufacturing:** Real-time telemetry retrieval for predictive maintenance and anomaly detection.
- **Smart Power Grids:** High-frequency meter analytics for dynamic load balancing and fault detection.
- **Healthcare & Remote Telehealth:** Fast biometric stream indexing for time-critical patient monitoring.

---

## Future Roadmap

- **Predictive Routing Models:** Integrate lightweight neural/ML query cost estimators for proactive cache warming and dynamic traffic adaptation.
- **Multi-Objective Energy-Aware Policies:** Introduce configurable carbon-intensity thresholds for automated cloud offloading.
- **Embedded Edge Deployment:** Optimize gateway footprint for resource-constrained edge nodes such as Raspberry Pi and ESP32 microcontrollers.

---

## Project Details

- **Timeline:** October 2026
- **Institution:** Dr. Vishwanath Karad MIT World Peace University (MIT-WPU)
