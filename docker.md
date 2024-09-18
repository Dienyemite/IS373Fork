# Docker Notes

documentation about WSL2, all stuff required to run docker and all that. just writing this so i dont forget lol
containerization (docker, kubernetes), virtualization, kernels, commands, etc

laying a skeleton out for now. this is ai generated slop for now.

## 1. WSL2 (Windows Subsystem for Linux 2)

- Virtualization technology that enables running Linux environments on Windows
- Provides better performance and compatibility compared to WSL1
- Required for running Docker on Windows

## 2. Containerization

### Docker

- Open-source platform for developing, shipping, and running applications
- Uses containerization to package applications with their dependencies
- Key components:
  - Docker Engine
  - Docker Images
  - Docker Containers
  - Dockerfile
  - Docker Compose

### Kubernetes

- Open-source container orchestration platform
- Automates deployment, scaling, and management of containerized applications
- Key concepts:
  - Pods
  - Services
  - Deployments
  - Nodes
  - Clusters

## 3. Virtualization

- Technology that creates virtual versions of computing resources
- Types:
  - Full virtualization
  - Paravirtualization
  - Hardware-assisted virtualization

## 4. Kernels

- Core component of an operating system
- Manages system resources and hardware
- Provides low-level services to other parts of the OS

## 5. Common Docker Commands

- `docker run`: Create and start a container
- `docker build`: Build an image from a Dockerfile
- `docker pull`: Download an image from a registry
- `docker push`: Upload an image to a registry
- `docker ps`: List running containers
- `docker images`: List available images

## 6. Docker vs. Virtual Machines

- Containers share the host OS kernel, while VMs have their own OS
- Containers are lighter and faster to start compared to VMs
- VMs provide stronger isolation but consume more resources
