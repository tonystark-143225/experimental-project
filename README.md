# DevOps Portfolio Demo

A simple static website showcasing DevOps skills, containerized with Nginx and deployable to Kubernetes.

## Project Structure

```
devops-portfolio-demo/
├── public/
│   └── index.html          # Enhanced portfolio page
├── Dockerfile              # Docker build instructions
├── nginx.conf              # Nginx configuration
├── k8s/
│   ├── deployment.yaml     # Kubernetes deployment manifest
│   └── service.yaml        # Kubernetes service manifest
└── README.md               # This file
```

## Features

- Responsive design with console-style interface
- Typing animation for skill listings
- Optimized for production deployment
- Gzip compression and caching enabled
- Security headers configured

## Local Development

1. Build the Docker image:
   ```bash
   docker build -t devops-portfolio:latest .
   ```

2. Run locally:
   ```bash
   docker run -p 8080:80 devops-portfolio:latest
   ```

3. Open http://localhost:8080 in your browser.

## Kubernetes Deployment

1. Build and push the Docker image to your registry:
   ```bash
   docker build -t your-registry/devops-portfolio:v1.0 .
   docker push your-registry/devops-portfolio:v1.0
   ```

2. Update the image in `k8s/deployment.yaml`.

3. Apply the manifests:
   ```bash
   kubectl apply -f k8s/
   ```

4. Check the deployment:
   ```bash
   kubectl get pods
   kubectl get services
   ```

## Customization

- Edit `public/index.html` to modify the content and styling.
- Adjust Nginx configuration in `nginx.conf` if needed.
- Modify Kubernetes resources in `k8s/` for scaling or additional features.

## Technologies Used

- HTML5, CSS3, JavaScript
- Nginx web server
- Docker containerization
- Kubernetes orchestration
