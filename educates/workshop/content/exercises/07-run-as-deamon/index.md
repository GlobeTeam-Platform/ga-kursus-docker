---
title: "Run as service"
---

To run the container as a service run
```execute
docker compose up -d
```

You should see 
```
[+] Running 1/0
 ✔ Container nginx  Running 
 ``` 
as a confirmation, that the container has been started with success.

To see the running container run
```execute
docker ps
```

You should now see 
```
CONTAINER ID   IMAGE                 COMMAND                  CREATED          STATUS        PORTS                               NAMES
4602acf12636   exercises-webserver   "/docker-entrypoint.…"   24 minutes ago   Up 1 second   0.0.0.0:80->80/tcp, :::80->80/tcp   nginx
```
Note the name if the container, is nginx, and not random generated one.

Open the App tab to see it is running like before
```dashboard:reload-dashboard
name: App
title: Open App
```
While the container is running
```editor:open-file
title: open html/index.html
file: ~/exercises/html/index.html
```

and change
```
<p>When it's running thru Dockerfile!</p>
```

to

```
<p>When it's running thru Docker-Compose!</p>
```

Save the file and open App Tab and see the changes
```dashboard:reload-dashboard
name: App
title: Open App
```

Note: The data is not build into the container, but instead directly mounted from the html directory, unlike the web:v1 and web:v2 we build earlier