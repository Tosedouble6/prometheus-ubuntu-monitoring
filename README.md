# Infrastructure Monitoring Stack: Prometheus + Grafana + Node Exporter

This repository contains a production-ready configuration for deploying a complete monitoring solution on a Linux server. It is optimized to automatically bypass regional Docker Hub connectivity registry errors using mirror proxies.

## Components

* **Prometheus**: Core timeseries database for metric collection.
* **Grafana**: Advanced visualization dashboard platform (default on port `3000`).
* **Node Exporter**: Host-level metrics collector (CPU, memory, disk, network usage).

## Prerequisites

Ensure you have **Docker** and **Docker Compose v2** installed on your target system.

## Quick Start

1. Clone this repository to your server:
   ```bash
   git clone https://github.com
   cd prometheus-ubuntu-monitoring
   ```

2. Start the monitoring stack in detached mode:
   ```bash
   docker compose up -d
   ```

3. Verify that all components are running correctly:
   ```bash
   docker compose ps
   ```

## Accessing Web Interfaces

* **Grafana Dashboards**: Access via `http://YOUR_SERVER_IP:3000` (Default Credentials: Login: `admin` / Password: `admin`).
* **Prometheus Target Manager**: Access via `http://YOUR_SERVER_IP:9090`.

## Configuration Notes

The `docker-compose.yml` file uses highly available mirror proxies (`docker.m.daocloud.io`) to guarantee smooth image pulling under strict network environments or local rate limits.
