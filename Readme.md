# GCP DevOps Project

This project establishes a CI/CD pipeline for deploying and updating Google Kubernetes Engine (GKE) clusters on Google Cloud Platform (GCP). The pipeline is orchestrated through GitHub actions and Google Cloud Build.

## Overview

- **Continuous Integration (CI):** GitHub branches are organized to manage different aspects of the project.

  - **main:** Represents the production-ready state. Merging into this branch triggers a CI/CD pipeline for deploying to the production GKE cluster.

  - **dev:** Represents the development environment. Any push to this branch triggers the CI/CD pipeline for deploying to the development GKE cluster.

## CI/CD Workflow

1. **GitHub Branching:**
   - Branches are created for different components of the project (e.g., Deployment, services, cloud build, etc.).

2. **Cloud Build:**
   - The CI/CD pipeline is defined in the `cloud-build.yaml` file.
   - Cloud Build automatically builds a Docker image, pushes it to Google Container Registry, and deploys the application to the specified GKE cluster and namespace.

## Folder Structure

- **Dockerfile:** Builds a Docker image for the Flask application.
  
- **app.py:** Contains the main Flask application with a basic route.

- **cloud-build.yaml:** Google Cloud Build configuration file for CI/CD pipeline.

- **gke.yaml:** Kubernetes Deployment and Service configuration for GKE deployment.

- **requirements.txt:** Specifies project dependencies, including Flask.

## Environments

- **Production (prod):** Represents the live environment. Changes in the main branch trigger deployment to the production GKE cluster.

- **Development (dev):** Represents the development environment. Any push to the dev branch triggers deployment to the development GKE cluster.

## Usage

- **Accessing the Application:** Once deployed, access the application at the LoadBalancer IP on port 80.

## Requirements

- Python 3.8
- Flask

## Notes

This CI/CD pipeline is designed to streamline the deployment process for GKE clusters on GCP. Adjust configurations as needed for specific project requirements.
