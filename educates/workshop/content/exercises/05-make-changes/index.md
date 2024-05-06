---
title: "Make changes"
---

Open html/index.html in the editor, and change the name of the student from `xxx`to your name, on line 14, and save the file again.

```editor:open-file
title: Open index.html
file: ~/exercises/html/index.html
```

Not build a new container image, with the new file, and a new version tag, by running
```execute
docker build -t web:v2 .
```

Run the new container image, by running 
```execute
docker run -p 80:80 web:v2
```

See the changes to the app in the `App` tab
To see the App click here.
```dashboard:reload-dashboard
name: App
title: Open App
```

You should now see that XXX has been replaced with your name.

If you run 
```execute
docker image ls
```

you should see the 2 images you have just created 
```
REPOSITORY   TAG       IMAGE ID       CREATED          SIZE
web          v2        1c62d541d0bf   49 seconds ago   240MB
web          v1        2b4224638951   16 minutes ago   240MB
```

Both images contains different files. so if you regreat the changes you made to v2, you can always run v1, and see the `Student XXX` image. 

This is big strength by running containers, that versions are controlled, and you have the options to go back, if you make mistakes.

---
**Talk in class about**

- Usecases for switching between docker images, and how to utilize this option in production.

- pro/cons about this way of working

---