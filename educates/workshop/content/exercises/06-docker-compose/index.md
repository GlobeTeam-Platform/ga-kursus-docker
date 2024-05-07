---
title: "Docker compose"
---

Docker Compose is a tool for defining and running multi-container Docker applications. 

With Compose, you use a YAML file to configure your application’s services. 

Then, with a single command, you create and start all the services from your configuration.

![docker compose](docker-compose.jpeg)

Open `docker-compose.yml` and examine the content of the file.
```editor:open-file
title: Open docker-compose.yml
file: ~/exercises/docker-compose.yml
```

---
**Talk in class about**

the different options in the file:

- Version
- Internal name
- Container name
- Build
- Ports
- Volumes (data is external from the container)
---

```execute
docker compose up
````

We have now build the container again, by defining both what to do, and where to find the Dockerfile with the line `build: .`

Open the App tab again, to see that the container is running again.

```dashboard:reload-dashboard
name: App
title: Open App
```

While the container is running
```editor:open-file
title: open html/index.html
file: ~/exercises/html/index.html
```
and replace 
```
src="Devops-toolchain.svg.png">
``` 
with 
```
src="docker-compose.jpeg">
``` 
and save.


Click here to refresh the App tab again, and see a more proper image.
```dashboard:reload-dashboard
name: App
title: Open App
```

Note: The data is not build into the container, but instead directly mounted from the html directory, unlike the web:v1 and web:v2 we build earlier
