# Deploying 2-Tier App with Application in Different Namespace and MySQL in Different Namespace

## Introduction
This guide outlines the steps to deploy a 2-tier application with the application component running in one namespace and MySQL running in another namespace.

## Prerequisites
- Access to a Kubernetes cluster
- `kubectl` command-line tool installed

## Steps

1. **Create Namespaces**
   - Create two namespaces: `app-ns` for the application component and `sql-ns` for MySQL.
     ```bash
     kubectl create namespace app-ns
     kubectl create namespace sql-ns
     ```

2. **Deploy MySQL**
   - Deploy MySQL in the `sql-ns` namespace.
     ```bash
     kubectl apply -f mysql-deployment.yaml -n sql-ns
     ```

3. **Deploy Application**
   - Deploy the application in the `app-ns` namespace, ensuring it is configured to connect to the MySQL service in the `sql-ns` namespace.



