---
title: "Trubleshoot running container"
---
## Shell

When trubleshooting a running container, a cli inside the container, is often a usefull tool. We will try this in the following steps

To get a terminal into the running container run
```execute
docker exec -it nginx /bin/bash
```

Your prompt should now have changed to something like this
```
root@4602acf12636:/usr/share/nginx/html# 
```
This means we are now running inside our container, as root.

To list the HTML directory run
```execute
ls /usr/share/nginx/html
```

You should now see the files from our `html` directory, from the mounted path inside our container.
```
Devops-toolchain.svg.png  docker-compose.jpeg  index.html
```

To exit out of the container run
```execute
exit
```
## Logs

Getting logs from a running container, is also a usefull way of trubleshooting, without loogin into it.

To get the logs from the container `nginx` run
```execute
docker logs nginx
```

The ooutput should look someting like this
```
2024/05/07 11:32:45 [notice] 1#1: worker process 24 exited with code 0
2024/05/07 11:32:45 [notice] 1#1: worker process 25 exited with code 0
2024/05/07 11:32:45 [notice] 1#1: worker process 27 exited with code 0
2024/05/07 11:32:45 [notice] 1#1: signal 29 (SIGIO) received
2024/05/07 11:32:45 [notice] 1#1: signal 17 (SIGCHLD) received from 22
2024/05/07 11:32:45 [notice] 1#1: worker process 22 exited with code 0
2024/05/07 11:32:45 [notice] 1#1: worker process 23 exited with code 0
2024/05/07 11:32:45 [notice] 1#1: signal 29 (SIGIO) received
2024/05/07 11:32:45 [notice] 1#1: signal 17 (SIGCHLD) received from 26
2024/05/07 11:32:45 [notice] 1#1: worker process 26 exited with code 0
2024/05/07 11:32:45 [notice] 1#1: worker process 29 exited with code 0
2024/05/07 11:32:45 [notice] 1#1: worker process 28 exited with code 0
2024/05/07 11:32:45 [notice] 1#1: exit
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: IPv6 listen already enabled
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2024/05/07 11:32:49 [notice] 1#1: using the "epoll" event method
2024/05/07 11:32:49 [notice] 1#1: nginx/1.25.5
2024/05/07 11:32:49 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14) 
2024/05/07 11:32:49 [notice] 1#1: OS: Linux 6.6.26-linuxkit
2024/05/07 11:32:49 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2024/05/07 11:32:49 [notice] 1#1: start worker processes
2024/05/07 11:32:49 [notice] 1#1: start worker process 22
2024/05/07 11:32:49 [notice] 1#1: start worker process 23
2024/05/07 11:32:49 [notice] 1#1: start worker process 24
2024/05/07 11:32:49 [notice] 1#1: start worker process 25
2024/05/07 11:32:49 [notice] 1#1: start worker process 26
2024/05/07 11:32:49 [notice] 1#1: start worker process 27
2024/05/07 11:32:49 [notice] 1#1: start worker process 28
2024/05/07 11:32:49 [notice] 1#1: start worker process 29
172.18.0.1 - - [07/May/2024:11:38:08 +0000] "GET / HTTP/1.1" 200 326 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/17.4.1 Safari/605.1.15" "192.168.65.1"
172.18.0.1 - - [07/May/2024:11:38:08 +0000] "GET /Devops-toolchain.svg.png HTTP/1.1" 304 0 "http://application-educates-cli-w01-s001.192.168.50.243.nip.io/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/17.4.1 Safari/605.1.15" "192.168.65.1"
172.18.0.1 - - [07/May/2024:11:38:29 +0000] "GET / HTTP/1.1" 200 330 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/17.4.1 Safari/605.1.15" "192.168.65.1"
172.18.0.1 - - [07/May/2024:11:38:29 +0000] "GET /Devops-toolchain.svg.png HTTP/1.1" 304 0 "http://application-educates-cli-w01-s001.192.168.50.243.nip.io/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/17.4.1 Safari/605.1.15" "192.168.65.1"
```

