**Credits to** 
 - https://github.com/jpetazzo/dind
 - https://hub.docker.com/_/docker/
 - https://blog.docker.com/2013/09/docker-can-now-run-within-docker/

The Container supports running docker daemon via systemd

**Running Docker Service in libvirtd in a container**
------------------------------------------
The container will need to be run in priviledged mode. e.g.
```
docker run -d  --privileged  -v /sys/fs/cgroup:/sys/fs/cgroup:ro hrishikesh/dockerdaemon-in-docker
```    

