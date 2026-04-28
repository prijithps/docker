# 🚀 Top 50 Docker Interview Questions

## 🟢 Section 1: Core Fundamentals (1–10)

### 1. What is Docker?

A platform for developing, shipping, and running applications in containers.

---

### 2. What problem does Docker solve?

* “Works on my machine” issue
* Dependency conflicts
* Environment inconsistency

---

### 3. What is a container?

A lightweight isolated environment that runs applications.

---

### 4. What is a Docker image?

A read-only template used to create containers.

---

### 5. What is Docker Engine?

Core component that builds and runs containers.

---

### 6. Difference between container and image?

* Image = blueprint
* Container = running instance

---

### 7. What is a Dockerfile?

Script with instructions to build an image.

---

### 8. What is Docker Hub?

A public registry to store and share Docker images.

---

### 9. Basic Docker commands?

```bash
docker build
docker run
docker ps
docker stop
docker images
```

---

### 10. Docker vs VM?

Docker shares OS kernel; VMs run full OS.

---

## 🟡 Section 2: Intermediate Concepts (11–25)

### 11. What is Docker architecture?

* Client
* Daemon
* Registry

---

### 12. What is a Docker layer?

Each instruction in Dockerfile creates a layer.

---

### 13. What is caching in Docker?

Reuses unchanged layers to speed up builds.

---

### 14. What is a volume?

Persistent storage independent of containers.

---

### 15. Bind mount vs volume?

Bind mount = host-controlled
Volume = Docker-managed

---

### 16. What is Docker networking?

Container communication mechanism.

---

### 17. Types of networks?

* bridge
* host
* overlay
* none

---

### 18. What is port mapping?

Mapping container port to host:

```bash
docker run -p 8080:80 nginx
```

---

### 19. What is Docker Compose?

Tool to run multi-container apps using YAML.

---

### 20. What is `.dockerignore`?

Excludes files from build context.

---

### 21. CMD vs ENTRYPOINT?

CMD = default command
ENTRYPOINT = fixed executable

---

### 22. What is ENV in Dockerfile?

Used to define environment variables.

---

### 23. What is EXPOSE?

Documents container ports.

---

### 24. What is COPY vs ADD?

COPY = simple copy
ADD = copy + extract + URL support

---

### 25. What is image tagging?

Versioning images:

```bash
docker tag app:v1 app:latest
```

---

## 🔵 Section 3: Advanced Concepts (26–40)

### 26. What is multi-stage build?

Reduces image size by separating build/runtime.

---

### 27. What is Docker Swarm?

Docker Swarm for clustering containers.

---

### 28. Swarm vs Kubernetes?

Swarm = simple
Kubernetes = powerful & scalable

---

### 29. What is orchestration?

Managing deployment, scaling, networking.

---

### 30. What is a registry?

Storage for Docker images.

---

### 31. What is a private registry?

Custom secure image repository.

---

### 32. What is container lifecycle?

Created → Running → Stopped → Removed

---

### 33. What is restart policy?

Defines container restart behavior.

---

### 34. What is health check?

Checks container status automatically.

---

### 35. What is Docker context?

Switch between environments (local/remote).

---

### 36. What is overlay network?

Multi-host networking in Swarm/K8s.

---

### 37. What is logging driver?

Controls log storage (json-file, syslog).

---

### 38. What is resource limit?

Control CPU/memory usage.

---

### 39. What is Docker secret?

Secure way to store sensitive data.

---

### 40. What is rootless Docker?

Run Docker without root privileges.

---

## 🔴 Section 4: Scenario-Based (41–50)

### 41. Container not starting?

* Check logs
* Inspect container
* Check ports

---

### 42. Image build slow?

* Optimize layers
* Use caching
* Reduce dependencies

---

### 43. Large image size?

* Use Alpine
* Multi-stage builds

---

### 44. Data lost after restart?

Use volumes.

---

### 45. Debug running container?

```bash
docker exec -it container bash
```

---

### 46. App not accessible?

* Check port mapping
* Check firewall

---

### 47. Container crashes repeatedly?

Check logs + memory limits.

---

### 48. Secure Docker?

* Non-root user
* Scan images
* Limit privileges

---

### 49. Docker in CI/CD?

* Build → Test → Push → Deploy

---

### 50. How Docker works with cloud?

Used with:

* Amazon Web Services
* Google Cloud Platform
* Microsoft Azure

---
