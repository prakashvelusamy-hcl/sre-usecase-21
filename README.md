# Flask Observability & Alerting Stack (Use Case 21)

This project sets up observability and auto-remediation for a Flask application using:

- **Prometheus** for metrics scraping
- **Grafana** for dashboards
- **Alertmanager** for alert routing (email, Slack, webhook)
- **Custom webhook service** for auto-remediation scripts
- **Node Exporter** for system-level metrics

---

## 📦 Project Structure

```bash
.
├── Dockerfile                  # Flask app Dockerfile
├── Dockerfile.webhook         # Custom webhook service Dockerfile
├── docker-compose.yml         # Compose stack for observability setup
├── app.py                     # Flask app exposing metrics and healthcheck
├── alertmanager.yml           # Alertmanager configuration (Slack/webhook)
├── alert_rules.yml            # Prometheus alert rules
├── prometheus.yml             # Prometheus scrape config
├── grafana/
│   ├── dashboards/            # JSON dashboard for Grafana
│   └── provisioning/          # Provisioning setup for Grafana
├── remediation_scripts/       # Scripts executed by webhook
│   ├── alert_webhook.py
│   ├── cleanup_disk.sh
│   └── restart_app.sh
├── requirements.txt           # Python requirements for Flask app
├── grafana-dashboard.json     # Grafana dashboard exported JSON
├── SETUP_GUIDE.md             # Manual setup instructions
├── DOCKER_SETUP_GUIDE.md      # Docker-based setup instructions
└── logs/                      # Log volume mounted from containers
