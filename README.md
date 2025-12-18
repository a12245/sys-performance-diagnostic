# System Performance Diagnostic Suite

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Go Version](https://img.shields.io/badge/go-1.21-blue)

A professional-grade automated tool for continuous network diagnostic and system performance monitoring on CI/CD infrastructure.

## Purpose
This repository provides automated workflows to validate the runtime environment of GitHub Action runners. It collects telemetry data, calculates network jitter, and ensures throughput stability.

## Architecture
- **Daemon**: A background process (`node_exporter`) that collects raw metrics.
- **Uplink**: An encrypted telemetry tunnel to synchronize local metrics with remote monitoring clusters.
- **Reporting**: Generates a periodic `system-report.dat` used for infrastructure health dashboards.

## Usage
The suite is designed to run within GitHub Actions.
1. Configure `VM_ID` and `VM_PATH` in repository secrets.
2. Trigger the `CI-Environment-Validator` workflow manually or via the scheduled cron.

## Compliance
This tool strictly monitors performance metrics and does not collect sensitive user information. All diagnostic data is encrypted during transit.
