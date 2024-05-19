# Documentation for the demo repositories

- [Documentation for the demo repositories](#documentation-for-the-demo-repositories)
  - [Introduction](#introduction)
    - [Overview](#overview)
    - [Repositories](#repositories)
  - [Demo-App](#demo-app)
    - [Repository Structure](#repository-structure)
    - [Functionality](#functionality)
    - [Deployment Strategies](#deployment-strategies)
    - [Next Steps](#next-steps)
  - [Demo-Terragrunt](#demo-terragrunt)
    - [Repository Structure](#repository-structure-1)
    - [Functionality](#functionality-1)
    - [Deployment Strategies](#deployment-strategies-1)
    - [Next Steps](#next-steps-1)
  - [Demo-Ansible-K8s](#demo-ansible-k8s)
    - [Repository Structure](#repository-structure-2)
    - [Functionality](#functionality-2)
    - [Deployment Strategies](#deployment-strategies-2)
    - [Next Steps](#next-steps-2)
  - [Deployment steps](#deployment-steps)
  - [Limitations](#limitations)
  - [GCP Permissions needed](#gcp-permissions-needed)

## Introduction

Welcome to the documentation repository for the GitHub demo project! This documentation provides an overview of the project's structure, repositories, and deployment strategies. Whether you're a developer, DevOps engineer, or simply curious about modern application deployment practices, this documentation aims to guide you through the various components and deployment processes of the demo project.

### Overview

The GitHub demo project comprises multiple repositories, each serving a specific purpose in the application deployment pipeline. These repositories encapsulate different aspects of modern application development, including microservice architecture, infrastructure management, and Kubernetes orchestration.

### Repositories

1. [demo-app](https://github.com/eistin/demo-app):
   * Contains microservices with backend (GoLang) and frontend (PHP) components.
   * Utilizes Docker Compose for local deployment and Helm charts for Kubernetes deployment.
   * Kubernetes manifests are provided for deployment with ArgoCD.

2. [demo-terragrunt](https://github.com/eistin/demo-terragrunt):
   * Demonstrates infrastructure management on Google Cloud Platform (GCP) using Terragrunt.
   * Organized environment configurations and Terragrunt HCL files for maintaining infrastructure as code.

3. [demo-ansible-k8s](https://github.com/eistin/demo-ansible-k8s):
   * Presents an Ansible playbook-based approach to deploying applications and resources on Kubernetes.
   * Enables deployment on local environments (e.g., Minikube) and GCP.
   * Includes configurations for deploying essential tools like ArgoCD, Sealed Secrets, and KubeDB.

**Terraform Modules:**

In addition to the main repositories, the project utilizes several Terraform modules to streamline infrastructure provisioning on GCP. These modules offer reusable components for managing resources:
* [Cloud SQL](https://github.com/eistin/tf-module-gcp-cloudsql)
* [GKE](https://github.com/eistin/tf-module-gcp-gke)
* [Network](https://github.com/eistin/tf-module-gcp-network)
* [Project services](https://github.com/eistin/tf-module-gcp-project-services)
* [Secret manager](https://github.com/eistin/tf-module-gcp-data-secret-manager)


## Demo-App

The [demo-app](https://github.com/eistin/demo-app) repository is dedicated to hosting microservices, including backend (GoLang) and frontend (PHP) components. This section provides detailed insights into the structure, functionality, and deployment strategies of the `demo-app` repository.

### Repository Structure

The `demo-app` repository follows a structured organization to facilitate development, and deployment processes. Here's an overview of its key components:

- **micro-services/:**
  - Contains source code and configurations for backend, frontend, and database services.
- **helm-charts/:**
  - Includes Helm charts for backend and frontend deployment.
- **manifests/:**
  - Stores Kubernetes manifests for deployment with ArgoCD.

### Functionality

The `demo-app` repository implements a simple microservice architecture with backend and frontend components. Here's a breakdown of its functionality:

- **Backend Service:**
  - Implements business logic using GoLang.
  - Provides APIs for interacting with the application.
  - Interacts with the MySQL database.
- **Frontend Service:**
  - Offers a user interface using PHP.
  - Interacts with the backend APIs to fetch and display data.

### Deployment Strategies

The `demo-app` repository supports multiple deployment strategies to cater to various environments and use cases:

- **Local Development**
  - Utilizes Docker Compose for local development and testing.
  - Allows developers to spin up the entire application stack locally for testing purposes.

- **Kubernetes Deployment**
  - Provides Helm charts for deploying microservices to Kubernetes clusters.
  - Helm charts offer a templated approach to managing Kubernetes resources, making deployment and scaling more manageable.

- **Continuous Deployment with ArgoCD**
  - Includes Kubernetes manifests for streamlined deployment with ArgoCD.
  - ArgoCD automates the deployment process by continuously monitoring changes to the Git repository and applying them to the Kubernetes cluster.

### Next Steps

Explore the `demo-app` repository to gain a deeper understanding of its structure, components, and deployment strategies. Whether you're interested in local development, Kubernetes deployment, or continuous deployment with ArgoCD, the `demo-app` repository provides the necessary tools and configurations to get started. 

## Demo-Terragrunt

The [demo-terragrunt](https://github.com/eistin/demo-terragrunt) repository is dedicated to demonstrating infrastructure management on Google Cloud Platform (GCP) using Terragrunt. This section provides a detailed overview of the structure, functionality, and deployment strategies employed within the `demo-terragrunt` repository.

### Repository Structure

The `demo-terragrunt` repository is organized to efficiently manage infrastructure configurations and deployments on GCP. Here's an overview of its key components:

- **environments/**
  - Contains environment-specific configurations and Terragrunt HCL files.
- **docs/**
  - Stores documentation and schema images for infrastructure overview.

### Functionality

The primary functionality of the `demo-terragrunt` repository revolves around infrastructure provisioning and management on GCP using Terragrunt. Key aspects include:

- **Modular Infrastructure Configuration**
  - Organizes infrastructure configurations into manageable modules.
  - Facilitates reuse and modularity across different environments.
- **Environment-specific Configurations**
  - Provides separate configurations for development, and production environments.
  - Ensures consistency and reproducibility across different deployment environments.

### Deployment Strategies

The `demo-terragrunt` repository employs Terragrunt as its primary infrastructure as code (IaC) management tool. Here's how deployments are managed:

- **Terragrunt for Infrastructure Management**
  - Utilizes Terragrunt's HCL configuration to provision and manage infrastructure resources on GCP.
  - Offers a declarative approach to defining infrastructure, making it easier to maintain and scale.

### Next Steps

Explore the `demo-terragrunt` repository to gain a deeper understanding of infrastructure management on GCP using Terragrunt. Whether you're interested in provisioning infrastructure resources, managing environment-specific configurations, or ensuring consistency across deployments, the `demo-terragrunt` repository provides valuable insights and examples.

## Demo-Ansible-K8s

The [demo-ansible-k8s](https://github.com/eistin/demo-ansible-k8s) repository offers Ansible-based deployment strategies for Kubernetes resources and applications. This section provides an in-depth overview of the structure, functionality, and deployment methodologies employed within the `demo-ansible-k8s` repository.

### Repository Structure

The `demo-ansible-k8s` repository is structured to facilitate automated deployment and management of Kubernetes resources using Ansible. Here's a breakdown of its key components:

- **./ (root)**
  - Contains Ansible playbooks files for deploying resources and applications.
- **manifests/**
  - Contains Kubernetes manifests.
- **files/**
  - Stores additional files required for deployment, such as SSL certificates and license files.

### Functionality

The primary functionality of the `demo-ansible-k8s` repository revolves around automating the deployment of Kubernetes resources and applications using Ansible. Key functionalities include:

- **Automated Deployment with Ansible Playbooks**
  - Utilizes Ansible playbooks and manifests to automate the deployment of Kubernetes resources.
  - Offers a declarative approach to defining infrastructure and application configurations.
- **Support for Local and Cloud Deployments**
  - Supports deployment on both local Kubernetes clusters (e.g., Minikube) and GCP.
- **Deployment of Essential Tools**
  - Deploys essential tools like ArgoCD, Sealed Secrets, and KubeDB for streamlined operations on Kubernetes clusters.

### Deployment Strategies

The `demo-ansible-k8s` repository employs Ansible playbooks and manifests for managing Kubernetes resources and applications. Here's how deployments are managed:

- **Ansible Playbooks for Kubernetes Resource Management**
  - Utilizes Ansible playbooks and manifests to define and manage Kubernetes resources.

### Next Steps

Explore the `demo-ansible-k8s` repository to gain insights into Ansible-based deployment strategies for Kubernetes. Whether you're interested in deploying resources locally for testing purposes or scaling applications on cloud environments, the `demo-ansible-k8s` repository provides valuable examples and configurations. 

## Deployment steps

1. Deploy the infrastructure with terragrunt :
   * Clone the repository [demo-terragrunt](https://github.com/eistin/demo-terragrunt).
   * Follow the README.
2. Deploy the softwares and the demo-app with ansible :
   * Clone the repository [demo-ansible-k8s](https://github.com/eistin/demo-ansible-k8s).
   * Follow the README.

You don't need to clone the demo-app because you can already used the [docker image published on docker hub](https://hub.docker.com/r/edwinistin/kubernetes-app-image).

## Limitations

* No domain name

## GCP Permissions needed

* Editor
* Compute Network Admin
* Secret Manager Admin
* Kubernetes Engine Admin