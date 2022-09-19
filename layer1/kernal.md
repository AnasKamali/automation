respond to msg from h/w
start and shcedule progs
control and organize storage

Docker manage kernal
manage kernal features
    uses "cgroupp" to contain processes
    uses "namespaces" to contain ntws
    uses "copy-on-write" filesystems to build image
make scripting distributed system "easy"

Docker is two programs : a client and a server
server receives cmds over a socket (either over a ntw or throug a "file")
The client can run inside a docker itself

file docker.sock --/var/run/docker.sock


client inside a container controling a server that outside container
docker run -ti --rm -v /var/run/docker.sock:/var/run/docker.sock docher sh ///usr/local/bin/docker:/usr/bin/docker
docker info
docker run -ti --rm ubuntu bash

