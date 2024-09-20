Welcome to the IS373 wiki!

> [!IMPORTANT]
> This Wiki is a work in progress. It will be updated periodically as we learn more about the technology.

# Docker Notes

documentation about WSL2, all stuff required to run docker and all that. just writing this so i dont forget lol
containerization (docker, kubernetes), virtualization, kernels, commands, etc

laying a skeleton out for now. this is ai generated slop for now.

## 1. WSL2 (Windows Subsystem for Linux 2)

<a href="https://github.com/ChrisAbdo/IS373/wiki/Containerization">
  <img src="https://media.licdn.com/dms/image/D5612AQEmgjGluk75Lw/article-cover_image-shrink_600_2000/0/1681454964046?e=2147483647&v=beta&t=fCN2Q81SbM8gJn35PM2bjLXy-z-RTWlX3iuI6b_arA4" alt="WSL2">
</a>

WSL2 is the second version of the Windows Subsystem for Linux, allowing Windows users to run a full Linux kernel in a lightweight virtual machine for improved compatibility and performance with Linux applications.

View the Wiki page here: [WSL2](https://github.com/ChrisAbdo/IS373/wiki/WSL2-(Windows-Subsystem-for-Linux)).


## 2. Containerization

<a href="https://github.com/ChrisAbdo/IS373/wiki/Containerization">
  <img src="https://www.simform.com/wp-content/uploads/2022/05/containerization-use-cases.png" alt="Containerization Image">
</a>

Containerization is the process of packaging software code and all its dependencies into a single unit—called a container—that can run uniformly and consistently across any computing environment.

View the Wiki page here: [Containerization](https://github.com/ChrisAbdo/IS373/wiki/Containerization).

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

![Alt text](https://www.cloud4u.com/upload/medialibrary/e69/what-is-a-virtualization-techology.png "Virtualization Diagram")

View the Wiki page here: [Virtualization](https://github.com/ChrisAbdo/IS373/wiki/Virtualization).

- Technology that creates virtual versions of computing resources
- Types:
  - Full virtualization
  - Paravirtualization
  - Hardware-assisted virtualization

## 4. Kernels

![Alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Kernel_Layout.svg/1200px-Kernel_Layout.svg.png "Kernel Diagram")

View the Wiki page here: [Kernels](https://github.com/ChrisAbdo/IS373/wiki/Kernels).

- Core component of an operating system
- Manages system resources and hardware
- Provides low-level services to other parts of the OS

## 5. Common Docker Commands

<a href="https://github.com/ChrisAbdo/IS373/wiki/Common-Docker-Commands">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20230613115937/Docker-Cheatsheet.webp" alt="Docker Command Images">
</a>

Docker commands are essential for managing containers and images effectively, providing a comprehensive set of tools for developers. This guide covers basic commands, container and image management, networking, and Docker Compose.

View the Wiki page here: [Common Docker Commands](https://github.com/ChrisAbdo/IS373/wiki/Common-Docker-Commands).


## 6. Docker vs. Virtual Machines

<a href="https://github.com/ChrisAbdo/IS373/wiki/Docker-vs.-Virtual-Machines">
  <img src="https://miro.medium.com/v2/resize:fit:1163/1*KtazvJZ-IX6aoq3jCjD5tA.png" alt=" Docker vs. Virtual Machines">
</a>

Docker and virtual machines (VMs) are both virtualization technologies, but they differ significantly in architecture and use cases. Docker containers share the host OS kernel, making them lightweight and faster to start, while VMs run on hypervisors with their own OS, providing stronger isolation at the cost of resource consumption.

View the Wiki page here: [Docker vs. Virtual Machines](https://github.com/ChrisAbdo/IS373/wiki/Docker-vs.-Virtual-Machines).
