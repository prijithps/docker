

**75. Docker Container Exits Immediately, how will you troubleshoot?**

* Check container logs: `docker logs <container_id>`
* Run container in interactive mode: `docker run -it <image> /bin/bash`
* Ensure a foreground process is running (container exits if main process ends).
* Verify `CMD`/`ENTRYPOINT` in Dockerfile.

---

**76. What is the purpose of EXPOSE in Dockerfile?**

* `EXPOSE` only documents which ports the containerized app listens on.
* It does **not** publish ports to the host.
* To access from host, you still need `docker run -p hostPort:containerPort`.

---

**77. Port is Not Accessible on localhost even after Port mapping in Docker**

* Ensure app inside container is listening on `0.0.0.0`, not just `127.0.0.1`.
* Confirm mapping: `docker ps` → shows published ports.
* Check firewall / security groups.
* Correct run command: `docker run -p 8080:80 <image>`

---

**78. Data lost when container stops and restarts, How will you fix it?**

* By default, container data is ephemeral.
* Use **Volumes** or **Bind Mounts**:

  * `docker run -v mydata:/app/data <image>`
  * or `docker run -v /host/path:/container/path <image>`

---

**79. You made change in your code, rebuilt the image, but the change isn’t reflected?**

* Check Dockerfile caching (use `--no-cache`).
* Ensure correct build context (files copied via `COPY . .`).
* Confirm container is using new image (remove old one).
* Stop and remove old container before running new.

---

**80. App Crashes with "Permission Denied" in Container but works fine on localhost.**

* File permissions or user mismatch inside container.
* Use proper ownership (`chown`, `chmod`).
* Run as correct user in Dockerfile (`USER`).
* Mount volumes with correct permissions.

---

**81. Docker host is running out of disk space, How do you clean up?**

* Remove unused containers, networks, images, volumes:

  * `docker system prune -a`
* Clean dangling volumes:

  * `docker volume prune`
* Check `/var/lib/docker` for large data.
* Use monitoring to prevent buildup.

* Perfect 👍 Here are copy-paste friendly answers for **82 to 86** from your screenshot:

---

**82. How will you Debug a Live Container?**

* Attach to container shell:

  * `docker exec -it <container_id> /bin/bash`
* View logs:

  * `docker logs -f <container_id>`
* Inspect container details:

  * `docker inspect <container_id>`
* Monitor processes:

  * `docker top <container_id>`

---

**83. Which container registry do you use in your organization?**

* Common registries: **Docker Hub, AWS ECR, GCP Artifact Registry, Azure ACR, Harbor, JFrog Artifactory, GitHub Container Registry.**
* Answer depends on company setup (e.g., “We use AWS ECR for private images and Docker Hub for public base images”).

---

**84. Explain the difference between CMD and ENTRYPOINT in Docker.**

* **CMD**: Provides default arguments for container execution, can be overridden at runtime.
* **ENTRYPOINT**: Defines the main executable that always runs, even if you pass extra arguments.
* Best practice: Use **ENTRYPOINT** for the main process, and **CMD** for default parameters.

---

**85. What docker commands you use on day-to-day basis?**

* `docker ps` → List running containers
* `docker images` → List images
* `docker logs <id>` → View logs
* `docker exec -it <id> /bin/bash` → Access container
* `docker build -t <tag> .` → Build image
* `docker run -d -p <host>:<container> <image>` → Run container
* `docker stop <id>` / `docker rm <id>` → Manage containers
* `docker system prune` → Cleanup

---

**86. When will you forcefully remove a container and how?**

* Use when a container is stuck, unresponsive, or won’t stop with normal commands.
* Command:

  * `docker rm -f <container_id>`


---
