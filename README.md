# jagritnokwal.com Kubernetes Deployment

This project contains Kubernetes manifests for deploying the [jagritnokwal.com](https://jagritnokwal.com) website.

## Features

- Containerized web application deployment
- Configurable via environment variables
- Scalable using Kubernetes deployments
- Service exposure via ClusterIP/LoadBalancer

## Structure

- `deployment.yaml` — Defines the website deployment
- `service.yaml` — Exposes the deployment
- `ingress.yaml` — (Optional) Configures ingress for domain routing

## Usage

1. Clone this repository:
    ```bash
    git clone https://github.com/j-Nokwal/jagritnokwal_k8s.git
    cd jagritnokwal_k8s
    ```

2. Apply the manifests:
    ```bash
    kubectl apply -f deployment.yaml
    kubectl apply -f service.yaml
    # Optional: kubectl apply -f ingress.yaml
    ```

3. Access the website via the configured service or ingress.

## Requirements

- Kubernetes cluster (local or cloud)
- kubectl installed

## Customization

- Update container image in `deployment.yaml` as needed
- Modify resource limits and environment variables for your use case

## License

MIT