# roboshop-dockerfiles

Overview
Dockerfiles, docker-compose, and service folders for developing and running Roboshop services locally or in containers.

Why this exists
To provide containerized builds and compose definitions for local development and testing.

Workflows
- Build service images
- Run docker-compose for local integration
- Push images to container registry for infra deployment

Actions (quick start)
1. Install Docker and docker-compose.
2. Build images: docker build -t <name> ./<service>
3. Run: docker-compose up -d

Key files
- docker-compose.yaml, service folders (cart, catalogue, frontend, mongodb, mysql, payment, rabbitmq, redis, shipping, user)

Notes
- Use environment files to configure services for different environments.
