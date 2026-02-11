# ESP32 Environmental Monitoring System

![ESP32](https://img.shields.io/badge/ESP32-Embedded-blue)
![C++](https://img.shields.io/badge/C%2B%2B-Firmware-orange)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED)
![Prometheus](https://img.shields.io/badge/Prometheus-Monitoring-E6522C)
![Grafana](https://img.shields.io/badge/Grafana-Visualization-F46800)

![Platform](https://img.shields.io/badge/Platform-ESP32%20%7C%20Linux-lightgrey)
![Status](https://img.shields.io/badge/Status-Active%20Development-success)
![License](https://img.shields.io/badge/License-MIT-green)

---

## Overview

This project implements an end-to-end environmental monitoring system using an **ESP32 microcontroller**, **Prometheus**, and **Grafana**.

The ESP32 collects temperature and humidity data from a digital sensor and exposes the measurements via a Prometheus-compatible `/metrics` HTTP endpoint. A Prometheus server running in Docker scrapes the metrics, and Grafana visualizes the data in real-time dashboards.

This project demonstrates skills across **embedded systems**, **networking**, and **cloud-native monitoring**.

---

## System Architecture


- ESP32 acts as a Prometheus scrape target
- Prometheus pulls metrics at fixed intervals
- Grafana visualizes time-series data

(See `/docs/architecture.md` for details.)

---

## Metrics Collected

- `esp32_temperature_celsius`
- `esp32_humidity_percent`
- `esp32_uptime_seconds`
- `esp32_wifi_rssi_dbm`
- `esp32_free_heap_bytes`

Metrics follow Prometheus naming and type conventions.

---

## Repository Structure

```bash
esp32-env-monitor/
├── esp32/ # ESP32 firmware (C++)
├── monitoring/ # Prometheus + Grafana (Docker)
├── docs/ # Architecture & setup documentation
└── README.md
```
---

## Quick Start

### 1. Flash the ESP32
- Configure WiFi credentials
- Flash firmware from `esp32/`
- Confirm `/metrics` endpoint is reachable

### 2. Start Monitoring Stack
```bash
cd monitoring
docker-compose up -d
```

### 3. Access Services

- Prometheus: http://localhost:9090
- Grafana: http://localhost:3000 (admin / admin)