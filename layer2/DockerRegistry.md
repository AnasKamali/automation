is a prog
stores layers and image
usually on port 5000
maint index
official by python docker registry 
Nexus
run it in docker
docker makes installing network services easy
registry is a docker service
docker run -d -p50000:5000 --restart=always --name registry registry:2
docker tag ubuntu:14.04 localhost:5000/mycompany/my-ubuntu:99
docker push localhost:5000/mycompany/my-ubuntu:99
--must establish authentication mechanism
--use docker registry page go to authentication 
Storage Option 
Local Storage
Or use cloude

Saving and loading Containers
docker save
docker load
//list image
docker images
//save image
docker save -o my-images.tar.gz my1 my2 my3
//check it save remove copy my1 my2 my3
docker rmi my1 my2 my3
docker image
// my1 my2 my3 gone
docker load -i my-images.tar.gz
** very useful to migrate btw storage types
** u can mail them




