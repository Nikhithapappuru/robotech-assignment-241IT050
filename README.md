# RoboTech – DevOps & Observability Setup

This repository contains the DevOps and Observability setup for the RoboTech assignment.

## Branch Used
- `devops-setup`

All CI/CD, monitoring, and observability-related configurations are implemented in this branch.

---

## CI/CD Pipeline (Jenkins)

- Jenkins is running locally using WSL.
- A Declarative Pipeline is defined using a `Jenkinsfile`.
- Pipeline is configured as **Pipeline as Code** using Git SCM.
- The pipeline performs the following stages:
  - Install Dependencies
  - Test / Lint
  - Build
- Pipeline fails automatically on errors.
- Pipeline execution is traceable to a specific Git commit.

---

## Environment Configuration

An example environment file is provided:

- `.env.example`

This file documents required environment variables such as:
- Docker Host IP
- Jenkins credentials

Where the actual secrets are not committed to the repository.

---

## Current Status

- CI/CD pipeline successfully configured and executed.
- Jenkins pipeline runs against the `devops-setup` branch.
- Further steps include:
  - Node Exporter setup
  - Prometheus metrics collection
  - Grafana dashboard creation
  - Webhook-based alerting for pipeline and monitoring events

---
### Monitoring Setup
- Installed **Node Exporter**
- Verified metrics exposure at `/metrics` endpoint
- Confirmed system-level metrics such as memory, CPU, and swap usage

---

 How to Verify

### Jenkins
- Access Jenkins at:
```
http://localhost:8080
```
- Trigger a build manually or via GitHub push
- Confirm successful pipeline execution in build history

### Node Exporter
- Ensure Node Exporter is running
- Open:
```
http://localhost:9100/metrics
```
- Verify Prometheus-style metrics are visible
