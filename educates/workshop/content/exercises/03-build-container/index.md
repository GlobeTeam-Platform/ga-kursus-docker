---
title: "Build container"
---


Switch back to the `Terminal` tab

To build your first container run 
```execute
docker build -t web:v1 .
```

This triggers a build of a image, with the name web1 and with a version tab of v1

Watch the build as it runs, thru every line of the Dockerfile

When it’s done, you should read Successfully tagged web:v1

To see the images local on the machine run
```execute
docker image ls
```
This should give you the following output
```
REPOSITORY   TAG       IMAGE ID       CREATED          SIZE
web          v1        5a8b7777b24d   33 seconds ago   212MB
```

This shows that you got an image with the name `web` with the tag `v1` that was created 33 seconds ago, with a size of 212mb

Note that you have not created a container yet. You have only created the image, from which you can deploy containers.