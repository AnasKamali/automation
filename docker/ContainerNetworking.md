
# Container Networking

## prog in cont are isolated from internet by default
## you can group your continers into "private" networks
## expose port to let connection in
## explicitly choose who can connect to whom
## private networks to connect between containers


# Expose a specfic port
## explicit specifies the port inside the container and outside
## exposes as many ports as you want 
## require coordination between containers
## make it easy to find the exposed container

docker run --rm -ti  -p 45678:45679 -p 45679:45679 --name echo-server ubuntu bash

-nc -lp 45678 | nc -lp 45679
docker run --rm -ti ubuntu bash
-nc localhost 45678
docker run --rm -ti ubuntu bash
-nc localhost 45679

# Exposing ports dynamically
## port inside container is fixed
## port on host is chosen from unused port
## allow many containers running with fixed port
## often used with service discovery service program

docker run --rm -ti -p 1234 -p 4321 --name echo-server ubuntu:14.04 bash

docker port echo-server
// list of port dynamically assign
# exposing udp port
docker run -p outside-port:inside-port/ protocol(tcp/udp)
docker run -p 1234:1234/udp

# connecting between container
## using virtual network
docker network create <network name>

docker run --rm -ti --net <network name> --name <container name> ubuntu:14.04 bash
-ping <container name2>

docker run --rm -ti --net <network name> --name <container name2> ubuntu:14.04 bash
-ping <container name>

docker network create <network name for specific server>
docker network connect <network name for specific server>  <container name>
docker run --rm -ti --net <network name for specific server> --name <container name3> ubuntu:14.04 bash
-ping <container name>
-- allowed
-ping <container name2>
-- not allowed