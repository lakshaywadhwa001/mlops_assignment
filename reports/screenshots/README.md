# Deployment Evidence

Local Minikube deployment verified on 2026-10-19. Screenshots document Kubernetes workloads, API endpoints, Grafana monitoring, GitHub Actions CI, and live kubectl/curl verification. See `../FINAL_REPORT.md` for results and `../../README.md` for setup and local API access.

The end-to-end pipeline video is hosted on Google Drive: [watch the recording](https://drive.google.com/file/d/1ZjDVIeZ9_H_q8ydrz-FwBvNCeN9P8ndM/view?usp=sharing).

## Screenshot inventory

| File | Contents |
|------|----------|
| `01-kubernetes-workloads.png` | Kubernetes workloads view showing all pods running |
| `02-health-endpoint.png` | `GET /health` returning `{"status":"ok","model_loaded":"true"}` |
| `03-predict-endpoint.png` | `POST /predict` returning prediction, label, confidence, and probabilities |
| `04-grafana-dashboard.png` | Grafana Heart Disease API dashboard — request rate, p95 latency, status-class breakdown, API target up |
| `05-grafana-dashboard-continued.png` | Grafana dashboard continued — same panels, ~1 minute later |
| `06-github-actions-success.png` | GitHub Actions CI run showing successful `quality-and-training` job |
| `07-fastapi-swagger-ui.png` | FastAPI Swagger UI listing `GET /health` and `POST /predict` endpoints |
| `08-fastapi-swagger-predict-body.png` | Swagger `/predict` request body schema with all 13 feature fields |
| `09-fastapi-swagger-predict-response.png` | Swagger `/predict` response schemas (200 success, 422 validation error) |
| `10-fastapi-swagger-schemas.png` | Swagger data model schemas: `HeartDiseaseInput`, `PredictionResponse`, validation types |
| `11-fastapi-swagger-health-schema.png` | Swagger `/health` endpoint with 200 response schema |
| `12-github-actions-ci-steps.png` | GitHub Actions CI job step log — all steps green including lint, tests, train, container build, smoke test |
| `13-kubectl-pods-health-check.png` | VS Code terminal: `kubectl get pods,services -n heart-disease` + `curl /health` returning `model_loaded: true` |
| `14-kubectl-predict-curl.png` | VS Code terminal: `curl /predict` returning `{"prediction":0,"label":"no_disease","confidence":0.5901,...}` |
