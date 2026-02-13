# Prometheus

This Prometheus instance scrapes environmental metrics from an ESP32 device.

## Scraped Metrics
- esp32_temperature_celsius
- esp32_humidity_percent
- esp32_uptime_seconds
- esp32_wifi_rssi_dbm
- esp32_free_heap_bytes

## Configuration
Edit `prometheus.yml` to update the ESP32 IP address.

## Access
Prometheus UI: http://localhost:9090
