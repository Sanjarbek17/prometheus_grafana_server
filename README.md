# Prometheus & Grafana Monitoring Stack

A lightweight, containerized monitoring solution featuring Prometheus for metrics collection, Grafana for visualization, and Node Exporter for system-level metrics.

## 🚀 Features

- **Prometheus**: Time-series database and monitoring system.
- **Grafana**: Data visualization and dashboarding tool.
- **Node Exporter**: Exposes hardware and OS metrics from the host.
- **Dockerized**: Easy to deploy and manage using Docker Compose.
- **Persistence**: Data is preserved across restarts using Docker volumes.

## 🛠️ Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## 🏃 Quick Start

1. **Spin up the stack:**
   ```bash
   docker compose up -d
   ```

2. **Verify containers are running:**
   ```bash
   docker compose ps
   ```

## 🌐 Accessing the Services

| Service | URL | Default Credentials |
| :--- | :--- | :--- |
| **Grafana** | [http://localhost:3007](http://localhost:3007) | `admin` / `admin` |
| **Prometheus** | [http://localhost:9097](http://localhost:9097) | None |
| **Node Exporter** | [http://localhost:9107](http://localhost:9107) | None |

## ⚙️ Configuration

### Prometheus
The `prometheus.yml` file defines the scrape targets. By default, it is configured to scrape:
- Prometheus itself (`localhost:9090`)
- Node Exporter (`node_exporter:9100`)

### Grafana
- **First Login**: You will be prompted to change the default password (`admin/admin`).
- **Data Source**: To add Prometheus as a data source in Grafana, use the URL `http://prometheus:9090`.

## 🧹 Maintenance

**Stop the services:**
```bash
docker compose stop
```

**Stop and remove containers (keeps data):**
```bash
docker compose down
```

**Stop and remove containers (wipes data volumes):**
```bash
docker compose down -v
```

## 📂 Project Structure

- `docker-compose.yml`: Defines the services, networks, and volumes.
- `prometheus.yml`: Configuration file for Prometheus scrape jobs.
