# Monitoring Stack for ARM Architecture

This project provides a complete monitoring stack for ARM-based systems, such as Raspberry Pi and Apple Silicon. It includes **Prometheus**, **Grafana**, **Node Exporter**, **Alertmanager**, and **Loki** to deliver a powerful and flexible solution for observing, logging, and alerting on your infrastructure.

## Components

- **Prometheus**: Collects metrics from various sources and stores them in a time-series database for analysis.
- **Grafana**: Provides visualization dashboards, enabling you to create real-time monitoring and alerts.
- **Node Exporter**: Collects and exports hardware and OS metrics from the host system to Prometheus.
- **Alertmanager**: Manages and dispatches alerts from Prometheus, allowing integration with other notification systems.
- **Loki**: A log aggregation system optimized for searching logs in Grafana.

## Prerequisites

- ARM-based system (e.g., Raspberry Pi, Apple Silicon Mac)
- Docker and Docker Compose installed on your system

## Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/rhoribe/docker-monitoring-stack-arm
    cd docker-monitoring-stack-arm
    ```

2. **Create environment files** (optional):
    - Customize environment variables such as alert routes, Grafana login, and more by creating `.env` files for the stack services.

3. **Start the stack**:
    ```bash
    docker-compose up -d
    ```

   This command will start Prometheus, Grafana, Node Exporter, Alertmanager, and Loki in Docker containers on ARM architecture.

4. **Access Grafana**:
    - Once all containers are up, open Grafana in your browser at `http://localhost:3000`.
    - Default login credentials:
        - **Username**: `admin`
        - **Password**: `admin`

5. **Configure Grafana Dashboards**:
    - Import dashboards for Prometheus metrics, Node Exporter, and Loki logs to get detailed visualizations of your system’s health.

## Configuration

### Prometheus
- The configuration file for Prometheus, `prometheus.yml`, includes the scrape targets for Node Exporter and Alertmanager.
- Adjust the scrape intervals or add more targets as needed.

### Alertmanager
- Alertmanager is configured to send alerts based on custom rules defined in `rules.XPTO.yml`.
- Customize alert notifications and routes according to your preference.

### Loki
- Loki is configured to collect logs for Grafana visualization.


## Supported Features

- **Metrics Collection**: CPU, memory, disk usage, and network performance.
- **Logging**: Collect logs from applications and system files.
- **Alerts**: Custom alert rules for CPU/memory thresholds, availability, and system health.

## System Requirements

- ARM-based architecture (Raspberry Pi, MacOS M1, M2, M3, M4)
- Docker installed

## Troubleshooting

If you encounter issues, try the following:

- **Check container logs**:
    ```bash
    docker-compose logs <service-name>
    ```
- **Restart the stack**:
    ```bash
    docker-compose restart
    ```
- **Review Prometheus scrape targets**: Make sure all services are listed in `prometheus.yml` and that their IPs/ports are accessible.

## Contributing

Feel free to submit pull requests or open issues to help improve this stack.

## License

This project is licensed under the MIT License.