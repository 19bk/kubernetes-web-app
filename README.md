# Kubernetes Web Application Deployment

This repository contains a Kubernetes YAML manifest for deploying a web application in a multi-zone cluster. The solution is designed to be fault-tolerant and resource-efficient based on the following parameters:

- **Multi-Zone Cluster**: The application runs across three zones for redundancy.
- **Resource Management**: The application starts with higher CPU usage (burst) and stabilizes around 0.1 CPU and 128Mi memory usage after initialization.
- **Scaling**: The application experiences peak load during the day and lower traffic at night. A Horizontal Pod Autoscaler (HPA) dynamically scales the number of pods from 1 (low load) to 6 (peak load).
- **Fault Tolerance**: By distributing pods across zones and using probes for health checks, the deployment ensures high availability.

## Files

- `deployment.yaml`: The main Kubernetes manifest file for deploying the application and setting up scaling and resource management.

## Usage

1. Apply the manifest to your Kubernetes cluster:
   ```bash
   kubectl apply -f deployment.yaml
