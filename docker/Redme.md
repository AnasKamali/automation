//tool docker desktop
//wsl for windows 
//hypervisor on 
```diff
docker basic commands
+ docker images
//Repository Tag Image Id Created Size
+ docker ps -a
//ps ~~ process status
+ docker run -ti ubuntu:latest bash
//terminal interactive

//once container stoped all file will be gone
+ docker commit <container-name> <my-image-name>
        or
+ docker commit <container-id>
+ docker tag <image-id> <my-image name>

//last container
+ docker ps -l

//remove container after exit
+ docker run --rm -ti ubntu sleep 5
+ docker run -ti ubntu bash -c "sleep 3; echo all done"

//detach container
+ docker run -d -ti ubntu bash
//docker attach container
+ docker attach <container name>
//detach from runing ctrl + p, ctrl+q

//running more things in container
+ docker exec -ti <container name> bash

+ docker run --name example -d ubntu bash -c "lose /etc/password"
//docker logs for container
+ docker logs example

//stop and remove container
+ docker kill <container name>
+ docker rm <container name>

//resource constraints
+ docker run --memory <max allowed memory> <image name> command
docer run --cpu-shares relative to other container
+ docker run --cpu-quota to limit in general

- dont let your container fetch dependency when they start
- dont leave imp stuff in unamed stopped container
```


