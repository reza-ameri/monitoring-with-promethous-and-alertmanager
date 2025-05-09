'''text
# Monitoring Stack with Prometheus, Alertmanager, Grafana and Node Exporter

This project sets up a complete containerized monitoring stack using Docker. It includes:

- **Prometheus** – for metrics collection
- **Alertmanager** – for sending alerts based on Prometheus rules
- **Grafana** – for visualizing metrics
- **Node Exporter** – for collecting system-level metrics

## 📦 Components

| Service        | Description                                  | Port |
|----------------|----------------------------------------------|------|
| Prometheus     | Metrics scraper and time series database     | 9090 |
| Alertmanager   | Alert management and routing system          | 9093 |
| Grafana        | Dashboard and visualization tool             | 3000 |
| Node Exporter  | System metrics exporter                      | 9100 |

## 🧱 Architecture

All services are containerized and run via `docker-compose`. Prometheus scrapes metrics from Node Exporter and itself. Grafana uses Prometheus as a data source. Alertmanager is integrated with Prometheus for custom alerting.


                      +-------------------+          +--------------------+
                      |     Prometheus    | ------>  |       Grafana      | ----------
                      +--------------------           --------------------           |
                        ^              |                                             |
                        |              v                                             v
   +----------------+   |         +-------------------+                     Users view dashboards
   | Node Exporter |---+         |   Alertmanager     |
   +----------------+             +-------------------+
                                       |
                                       v
                                Notifications
                                       |
                                       v
                            Email / Slack (optional)


- **Prometheus** scrapes metrics from **Node Exporter**.
- **Grafana** queries **Prometheus** to visualize the data.
- **Prometheus** sends alerts to **Alertmanager**.
- **Alertmanager** handles notification delivery (email, Slack, etc.)




## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/reza-ameri/monitoring-with-prometheus-and-alertmanager.git
cd monitoring-with-prometheus-and-alertmanager

```markdown

