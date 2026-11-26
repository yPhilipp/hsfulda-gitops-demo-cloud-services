# Calendar Application Project

This project consists of a calendar application with event management functionality and its Helm chart for Kubernetes deployment.

## Template status
![Template status: unready](https://img.shields.io/badge/Template%20status-unready-red)

## Project Structure

- **[calendar-app/](calendar-app/)** - Contains the monolithic calendar application code
- **[calendar-chart/](calendar-chart/)** - Contains the Helm chart for deploying the application to Kubernetes
- **[calendar-argo/](calendar-argo/)** - The ArgoCD application files needed to install this
- **[calendar-flux/](calendar-flux/)** - The FluxCD configuration files needed to install this (Advanced users only)
- **[docker-compose.yml](docker-compose.yaml)** - Docker Compose file for running the application locally

## Calendar App

A simple calendar application with event management functionality, built as a monolithic application.

### Features

- Add new events with name and date
- View all events in a visually appealing interface
- Delete events
- Responsive design that works on mobile and desktop

### Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: MariaDB
- **Frontend**: HTML, CSS, JavaScript, Axios

### Running with Docker Compose

To run the application using Docker Compose:

1. From the root directory, run:
   ```
   docker compose up
   ```

2. Access the application at `http://localhost:3000`

## Helm Chart

The Helm chart in the `calendar-chart` directory allows for easy deployment to Kubernetes clusters.

For more information on deploying with Helm, see the [Helm Chart README](calendar-chart/README.md).

## ArgoCD Setup

The project includes an ArgoCD setup for continuous deployment to Kubernetes. The setup files are located in the [`argocd-setup`](argocd-setup) directory.

## FluxCD Setup (Advanced users only)

The project includes an FluxCD setup for continuous deployment to Kubernetes. The setup files are located in the [`calendar-flux`](calendar-flux) directory.

## GitHub Actions CI/CD

The project includes a GitHub Actions workflow for continuous integration and deployment. The workflow file is located at `.github/workflows/docker-ci.yaml`.

### CI/CD Pipeline Features

- Automatically builds the Docker image when triggered
- Pushes the image to ghcr.io with both `latest` and commit SHA tags
- Pushes the helm chart to ghcr.io with using the GitHub run number as a version
- Can be manually triggered using GitHub's workflow_dispatch feature
- Uses Docker Buildx for efficient builds

## License

This project is licensed under the MIT License.