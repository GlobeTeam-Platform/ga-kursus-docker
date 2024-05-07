---
title: "Advanced Docker-Compose"
---

In this task, we are going to look at a more advanced Multi container Wordpress app. Note we have multiple docker-comose files, and therefore we need to point to the .wp docker-compose file.

```editor:open-file
title: Open docker-compose.wp.yml
file: ~/exercises/docker-compose.wp.yml
```

---
**Talk in class about**

- Multiple containers
- Env variables
- Links between containers
- Volumes
- Depends on
- restart policy
---

To start the container run
```execute
docker compose -f docker-compose.wp.yml up
```

Look at the images get pulled, and the install process runs.

The db will start first, and when it's running, then the wordpress container will start.

Open the App tab and finish the setup
```dashboard:reload-dashboard
name: App
title: Open App
```

See that you now have a full Wordpress site, with seperate Web and DB instances.

Everything should be fully working.

Press `ctrl + c` when you are done, to stop the container.