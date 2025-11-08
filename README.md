# grafana-prometheus-production

**Problem Statement:** How to explain Grafana Prometheus Observability stack deployment in Production?

**Answer:** Suppose you have your Terraform module-based AWS EKS Clusters setup, along with your application workloads running as pods inside these.

**Architectural Diagram:**

<img width="898" height="367" alt="image" src="https://github.com/user-attachments/assets/59d9d16a-481d-4b64-83c2-53b219eef3eb" />

You want to deploy Grafana and Prometheus for monitoring and observability of these workloads and the EKS clusters as well. 

We utilize the kube-prometheus-stack Helm chart to deploy Grafana and Prometheus in the EKS cluster via the Terraform Helm provider.

Prometheus scrapes metrics from various Kubernetes components and application workloads, 

while Grafana provides a powerful dashboarding solution to visualize these metrics.

**Implementation Steps:**

We will utilize the Terraform Helm provider to deploy the kube-prometheus-stack chart.

Prometheus: We first deploy Prometheus to collect metrics from the Kubernetes cluster and application workloads.

Prometheus Mimir: We deploy Prometheus Mimir for long-term storage of metrics, enabling scalable and durable metric storage.

Grafana: Finally, we deploy Grafana to visualize the collected metrics through customizable dashboards.

Grafana will be configured to connect to Prometheus Mimir as a data source. 

allowing users to create dashboards that provide insights into the health and performance of the EKS clusters and application workloads.

Grafana will have a database backed by PostgreSQL for storing user data, dashboards, and configurations.

Then, we create alerts and a dashboard with a Terraform module to monitor the EKS clusters and application workloads effectively.

All Terraform code will be organized in modules for better reusability and maintainability.

The alerts and dashboards will be defined in a JSON file and referenced in the Terraform module for Grafana.

And, we put everything together in a GitLab repository for version control and collaboration.
