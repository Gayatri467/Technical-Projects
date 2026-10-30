
# Kubernetes Deployment

## 1. Overview

This project focuses on deploying the MRT DuckDB Analytics application in a Kubernetes environment using Docker Desktop Kubernetes.

The deployment demonstrates how to run the application inside Kubernetes, manage application pods, expose the application through a Kubernetes Service, and access the dashboard.

## 2. Project Objectives

- Understand Kubernetes deployment concepts.
- Deploy the MRT DuckDB Analytics application in Kubernetes.
- Configure Kubernetes Deployment resources.
- Manage application pods.
- Expose the application using a NodePort Service.
- Verify application availability inside Kubernetes.

## 3. Technologies Used

- Kubernetes
- Docker Desktop
- Docker
- YAML
- kubectl
- Flask
- DuckDB
- Apache Parquet

## 4. Kubernetes Environment Setup

Docker Desktop Kubernetes was used to provide the local Kubernetes environment.

The Kubernetes context was configured as:

```bash
kubectl config current-context
```

The expected context is:

```text
docker-desktop
```

## 5. Deployment Configuration

A Kubernetes YAML configuration file named `mrt-duckdb.yaml` was created.

It defines the resources required to deploy the MRT DuckDB Analytics application.

The configuration includes:

- Deployment: Manages the application pod.
- Container: Runs the MRT DuckDB application.
- Service: Exposes the application through a NodePort.

## 6. Creating the Kubernetes Deployment

Apply the Kubernetes configuration using:

```bash
kubectl apply -f mrt-duckdb.yaml
```

Check the deployment status:

```bash
kubectl get deployments
```

Check the running pods:

```bash
kubectl get pods
```

## 7. Service Configuration

A Kubernetes NodePort Service was configured to expose the application.

The service uses the following port mapping:

| Port Type | Port |
|---|---:|
| Application Port | 5000 |
| NodePort | 30500 |

Check the service using:

```bash
kubectl get services
```

## 8. Accessing the Application

The MRT DuckDB Analytics dashboard was accessed locally after deployment.

The dashboard was tested using:

```text
http://127.0.0.1:5001
```

Port 5001 was used because port 5000 was already occupied locally.

## 9. Deployment Verification

The deployment was verified using Kubernetes commands.

```bash
kubectl get deployments
kubectl get pods
kubectl get services
```

The application pod reached the running state, and the dashboard was accessible.

The Parquet dataset was also checked inside the application container to verify that the required data file was available.

## 10. Conclusion

This project demonstrates how a Flask-based MRT DuckDB Analytics application can be deployed and managed using Kubernetes.

Docker Desktop Kubernetes, Deployment resources, Pods, and NodePort Services were used to run and access the application in a local Kubernetes environment.

