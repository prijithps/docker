

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

---
