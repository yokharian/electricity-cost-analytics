# 🧠 PRD: Electricity Cost Analytics

## tl;dr

Backend microservices architecture for processing and serving statistical analyses of electricity costs from industrial IoT sensors. FastAPI services ingest metering data, compute cost analytics using Pandas, and expose results via REST APIs — with Docker for reproducible deployments.

---

## 🎯 Goals

- **Microservices Architecture**: Decompose electricity cost analytics into independent, deployable services
- **Statistical Analysis**: Compute electricity cost aggregations, trends, and KPIs using Pandas
- **REST API**: Expose analytics endpoints for consumption by BI tools (Grafana, Power BI) and frontend dashboards
- **Design Patterns**: Apply Strategy, Factory, and Repository patterns for maintainable, extensible code
- **Containerization**: Docker-based deployment for consistent environments across dev and production

## 👤 User Stories

- As an **operations manager**, I want per-facility electricity cost breakdowns so I can identify savings opportunities
- As a **data analyst**, I want statistical endpoints (averages, peaks, trends) so I can build dashboards without raw data access
- As a **developer**, I want well-structured microservices with clean patterns so I can extend analytics without modifying core logic
- As a **DevOps engineer**, I want Docker-based deployments so I can run services consistently across environments

## 🔄 Data Flow

```text
1. IoT sensors send electrical measurements (voltage, current, power)
   ↓
2. Data ingestion service receives and validates metering data
   ↓
3. Storage layer persists raw measurements to time-series database
   ↓
4. Analytics service computes cost metrics using Pandas
   ↓
5. REST API exposes analytical endpoints
   ↓
6. BI tools (Grafana, Power BI) and frontend consume the API
```

## 🧱 Core Components

### API Layer (FastAPI)

- **Cost Analytics Endpoint**: Returns computed electricity costs per time period, facility, and meter
- **Statistical Summary Endpoint**: Aggregated metrics (averages, peaks, standard deviations)
- **Trend Analysis Endpoint**: Time-series trend data for cost forecasting
- **Health Check Endpoint**: Service availability and dependency status

### Analytics Engine

- **Cost Calculator**: Applies tariff rules and time-of-use pricing to compute costs
- **Statistics Module**: Pandas-based statistical computations (mean, median, peak, rolling averages)
- **Trend Analyzer**: Identifies cost trends and anomalies over configurable time windows

### Data Access Layer

- **Repository Pattern**: Abstracted database access with interchangeable backends (InfluxDB, Timestream)
- **Time-Series Queries**: Optimized queries for time-range and aggregation operations

### Infrastructure

- **Docker Compose**: Local development environment with all dependencies
- **Service Registry**: Each microservice registers its API contract

## 📚 References

- [Architecture Diagram](./diagram.puml)