```markdown
# Cloud-Native Microservices Demo & DevSecOps Platform

An enterprise-grade, highly scalable microservices architecture modeled after modern cloud-native deployment patterns, maintained and optimized by [rybnd](https://github.com/rybnd). This project serves as a production showcase for **Kubernetes cluster orchestration**, **Terraform infrastructure as code (IaC)**, and **automated DevSecOps pipelines**.

---

## 🚀 Engineering & DevOps Enhancements
- **Automated DevSecOps Pipeline**: Integrated GitHub Actions workflows featuring rigorous Kubernetes manifest validation (`kubeconform`) and continuous container vulnerability scanning (`Trivy`).
- **Infrastructure as Code (IaC)**: Automated provisioning of cloud environments and GKE/EKS clusters using modular Terraform configurations.
- **Advanced Observability**: Configured Prometheus and Grafana monitoring specifications for real-time telemetry, resource tracking, and pod health monitoring.
- **Resilient Architecture**: Engineered with strict CPU/memory resource requests, limits, and asynchronous communication patterns across multi-replica microservices.

---

## Application Overview

**Online Boutique** is a cloud-first microservices e-commerce application where users can browse items, manage shopping carts, and complete simulated purchases. 

The application consists of **11 microservices** written in diverse languages communicating over gRPC:

| Service | Language | Description |
| :--- | :--- | :--- |
| [`frontend`](/src/frontend) | Go | HTTP web server generating session IDs and rendering the storefront. |
| [`cartservice`](/src/cartservice) | C# | Manages user shopping carts backed by Redis. |
| [`productcatalogservice`](/src/productcatalogservice) | Go | Serves product lists, search queries, and catalog details. |
| [`currencyservice`](/src/currencyservice) | Node.js | Handles real-time currency conversion using European Central Bank rates. |
| [`paymentservice`](/src/paymentservice) | Node.js | Processes simulated credit card transactions. |
| [`shippingservice`](/src/shippingservice) | Go | Calculates shipping estimates and fulfills orders. |
| [`emailservice`](/src/emailservice) | Python | Dispatches simulated order confirmation emails. |
| [`checkoutservice`](/src/checkoutservice) | Go | Orchestrates checkout flows across payment, shipping, and email services. |
| [`recommendationservice`](/src/recommendationservice) | Python | Provides product recommendations based on cart contents. |
| [`adservice`](/src/adservice) | Java | Serves context-aware text advertisements. |
| [`loadgenerator`](/src/loadgenerator) | Python/Locust | Simulates continuous user traffic and shopping flows. |

---

## Architecture Diagram

[![Architecture of microservices](/docs/img/architecture-diagram.png)](/docs/img/architecture-diagram.png)

---

## Quickstart & Deployment

### 1. Requirements
- Google Cloud Project with billing enabled.
- Local shell environment equipped with `gcloud`, `git`, and `kubectl`.

### 2. Cluster Provisioning (Terraform)
Navigate to the `terraform/` directory to provision your infrastructure:
```sh
cd terraform
terraform init
terraform apply

```

### 3. Deploy Kubernetes Manifests

Apply the production-ready manifests to your cluster:

```sh
kubectl apply -f ./kubernetes-manifests/

```

### 4. Verify Pod Status

```sh
kubectl get pods

```

---

## Documentation & Guides

* [Development Guide](https://www.google.com/search?q=/docs/development-guide.md)
* [Terraform Infrastructure Configs](https://www.google.com/search?q=/terraform)
* [Kubernetes Manifests](https://www.google.com/search?q=/kubernetes-manifests)

```

```