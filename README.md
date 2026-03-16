*This project has been created as part of the 42 curriculum by bkwamme.*

# Inception

## Description
Inception is a project designed to introduce and deepen understanding of Docker and containerization concepts. The goal is to set up a secure, multi-container infrastructure using Docker Compose, featuring services such as Nginx, MariaDB, and WordPress. The project demonstrates how to orchestrate and manage these services efficiently, focusing on isolation, reproducibility, and automation.

The project uses Docker to encapsulate each service in its own container, ensuring modularity and ease of management. The provided sources include Dockerfiles and configuration files for each service, as well as scripts for initialization and setup.

### Main Design Choices
- **Service Isolation:** Each service (Nginx, MariaDB, WordPress) runs in its own container for better security and maintainability.
- **Custom Configuration:** Configuration files are provided for each service to allow fine-tuned control and customization.
- **Automation:** Scripts are used to automate setup tasks, such as database initialization and SSL certificate generation.
- **Docker Compose:** Used to orchestrate the multi-container setup, simplifying deployment and management.

### Comparison
- **Virtual Machines vs Docker:**
  - Virtual Machines emulate entire operating systems, consuming more resources and taking longer to start. Docker containers share the host OS kernel, making them lightweight, faster to start, and more efficient for microservice architectures.
- **Secrets vs Environment Variables:**
  - Environment variables are easy to use but less secure for sensitive data. Docker Secrets provide a more secure way to manage sensitive information, especially in production environments, by restricting access and encrypting data at rest and in transit.
- **Docker Network vs Host Network:**
  - Docker Network provides isolated, user-defined networks for containers, enhancing security and flexibility. Host Network allows containers to use the host’s networking stack directly, which can be less secure and is generally used for performance-critical applications.
- **Docker Volumes vs Bind Mounts:**
  - Docker Volumes are managed by Docker and are ideal for persistent, portable data storage. Bind Mounts map host directories/files into containers, offering more direct control but less portability and security compared to volumes.

## Instructions

### Prerequisites
- Docker
- Docker Compose

### Build and Run
1. Clone the repository:
   ```sh
   git clone <repo-url>
   cd inception
   ```
2. Build and start the containers:
   ```sh
   make
   # or
   make dup
   ```
3. To stop the containers:
   ```sh
   make down
   ```
4. To rebuild and restart:
   ```sh
   make re
   ```
5. To access a running container:
   ```sh
   make run s=<service-name>
   # Example: make run s=nginx
   ```

## Resources
- [Docker Documentation](https://docs.docker.com/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
- [MariaDB Documentation](https://mariadb.com/kb/en/documentation/)
- [Nginx Documentation](https://nginx.org/en/docs/)
- [WordPress Documentation](https://wordpress.org/support/article/)

### Use of AI
AI was used to assist in drafting documentation, generating configuration templates, and providing code suggestions for Dockerfiles and shell scripts. All critical configurations and scripts were reviewed and customized to meet project requirements.

---

For more details, refer to the configuration files and scripts in the `srcs/requirements/` directory.
