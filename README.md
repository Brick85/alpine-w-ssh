# Minimal Alpine Linux Docker Image with SSH for CI/CD

This repository provides a lightweight Docker image based on Alpine Linux with SSH pre-installed. It is designed to optimize CI/CD pipelines by eliminating the need to install SSH during each build or deployment step, saving valuable time.

## Features
- **Base Image:** Alpine Linux (minimal size and security-focused).
- **Pre-installed SSH:** Ready-to-use OpenSSH for deployment tasks.
- **Optimized for CI/CD:** Reduces setup time in deployment pipelines.

## Why Use This Image?
In many CI/CD setups, SSH is required for deployment tasks such as:
- Connecting to remote servers
- Executing deployment scripts
- Securely transferring files

By using this pre-configured image, you can save a few seconds in every CI/CD pipeline run, which adds up significantly over time.

## Usage

### Use in CI/CD
```yaml
deploy:                                                                         
    stage: deploy                                                               
    image: vitalbrick/alpine-w-ssh:latest                                       
    script:                                                                     
        - chmod 600 $DEPLOY_SSH_KEY                                             
        - ssh -i $DEPLOY_SSH_KEY -o StrictHostKeyChecking=no $HOST '/path/to/update.sh'
```

## Notes:
- This readme was created using AI.
