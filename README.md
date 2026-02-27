# industrial-sensor-fault-mlops
A full scale - industry level - MLOps project

# project structure

industrial-sensor-fault-mlops/
  apps/
    model_service/
    trainer/
  ml/
    data/
    models/
    evaluation/
    drift/
  infra/
    helm/
      platform/
      model-service/
      trainer/
    terraform/
      aws-k3s/
      aws-eks/        # optional later
      onprem-local/   # optional helper for kind
  ci/
    github-actions/
  docs/
    architecture.md

# architecture

EC2 (public)
│
├── k3s
│ ├── ingress-nginx
│ ├── platform namespace
│ │ ├── MLflow
│ │ ├── Postgres
│ │ ├── Grafana
│ │ └── Prometheus
│ └── apps namespace
│ ├── model-service
│ └── trainer
│
└── S3 bucket (MLflow artifacts)
    runbooks.md
    cost-control.md
