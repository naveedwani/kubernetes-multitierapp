# Kubernetes Multi-Tier Web App (Demo)

**Purpose:** Deploys a frontend and backend application in Kubernetes with services and ingress routing. Image names and resource definitions are placeholders.

## Components
- Frontend Deployment
- Backend Deployment
- ClusterIP Services for internal communication
- Ingress to route `/` to frontend and `/api` to backend

## Usage
1. Replace image references with your own container registry images.
2. Apply to a Kubernetes cluster:
   ```sh
   kubectl apply -f backend-deployment.yaml
   kubectl apply -f frontend-deployment.yaml
   kubectl apply -f service-backend.yaml
   kubectl apply -f service-frontend.yaml
   kubectl apply -f ingress.yaml
   ```
3. Configure DNS or port-forward to test routes.

## Notes
- Ingress assumes an NGINX ingress controller is installed.
