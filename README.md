# DevLaunch — Jenkins + Apache CI/CD Demo

A beginner-friendly static website project for practicing a Jenkins pipeline.

## Files
- `index.html` — website structure
- `style.css` — responsive styling
- `Jenkinsfile` — checkout, validate, and deploy pipeline

## Deployment assumptions
The supplied Jenkinsfile is designed for the local Docker Compose practice setup in which:
- Jenkins checks out this repository.
- The Jenkins container has a writable shared volume mounted at `/deploy`.
- Apache serves the same shared volume as its document root.

## Pipeline stages
1. Checkout repository source.
2. Validate that `index.html` and `style.css` exist.
3. Copy website files into `/deploy`.

This is a learning project, not a production deployment configuration.
