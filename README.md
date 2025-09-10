# Flask + Redis + Prometheus + Grafana

A simple demo application that shows how to:

- Build a **Flask app** that uses **Redis** for storage.
- Expose **Prometheus metrics** (hits, misses, request counts, latencies).
- Visualize everything in **Grafana dashboards**.

---

## 🚀 Features

- REST API with Flask + Redis:
  - `POST /items` → add key/value
  - `GET /items/<key>` → fetch value
  - `GET /items` → list all keys
- Prometheus metrics endpoint at `/metrics`
- Metrics included:
  - Cache hits / misses
  - HTTP request counts (by method, endpoint, status)
  - Request latency histogram
- Grafana dashboards to monitor hit ratio, latency, request volume

---

## 📦 Requirements

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/)

---

## ▶️ How to Run

```bash
# After clone repo
cd instrumented-flask-app

# Start everything
docker compose up -d

```
### Prometheus & Grafana

- **Prometheus**: available at [http://127.0.0.1:9090/](http://127.0.0.1:9090/)  
  Use it to explore raw metrics exposed by the Flask app at `/metrics`.

- **Grafana**: available at [http://localhost:3000/](http://localhost:3000/)  
  Default login: **admin / admin**

  1. Add a new data source:  
     - Type: **Prometheus**  
     - URL: `http://prometheus:9090`
  2. Import the provided dashboard:  
     - Go to **Dashboards → Import**  
     - Upload `./configs/grafana-dashboard.json`  
     - Select the Prometheus data source you just added


```
Run the ./run-test.sh script
```
