# Electricity Cost Analytics

Backend microservices for statistical analysis of electricity costs from industrial IoT sensor data.

## Tech Stack

- **Language**: Python
- **Framework**: FastAPI
- **Analytics**: Pandas
- **Database**: InfluxDB / AWS Timestream
- **Containerization**: Docker
- **Patterns**: Strategy, Factory, Repository

## How It Works

1. Electrical measurements are received from IoT sensors
2. Data ingestion service validates and stores raw metering data
3. Analytics service computes cost metrics using Pandas (tariffs, time-of-use pricing)
4. Statistical summaries and trend data are generated
5. REST API exposes results for BI tools and dashboards

## Features

- Per-facility electricity cost breakdowns
- Statistical analysis: averages, peaks, trends, rolling averages
- Time-of-use tariff calculation
- Repository pattern for swappable time-series backends
- Docker Compose for local development

## Architecture

See [diagram.puml](./diagram.puml) for system architecture.

## References

- [PRD](./prd.md)
- Blog post: [Data Processing Pipeline](https://yokharian.dev/posts/iot-electrical-bi-and-kpis-startup)