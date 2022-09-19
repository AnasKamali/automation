

either moves frames on a wire
ip layer move pakets to a local network
routing : forward packets between ntws
ports : address particular programs on a computer

## Briding
docker uses bridges to create virtual ntws in a computer
These are s/w switches
They control ethernet layer

# using host ntw
docker run -ti --rm --net=host ubuntu:16.04 bash
apt-get update && apt-get install bridge-utils
brctl show
//show bridges
bridge name bridge id  STP enable interfaces
docker0 8000.fe2o no 
br-36fa 8000.fe3o no
# BRIDGING

docker uses bridges to create virtual ntws in your computer
these are s/w switches
they control the Ethernet layer
you can turn off this protection with 
docker run --net-host options
# routing 
creates firewall rules to move packet btw ntws
NAT(ntw add translation)
changes the source address on the way out 
change the destination add on way back in
sudo iptables -n -L -t nat
docker run --net-host --privileged=true ubuntu bash
apt-get install iptables
iptables -n -L -t nat
docker run -ti --rm -p 8080:8080 ubuntu bash
docker run --net-host options
//we see port forwarding
DNA tcp --0.0.0.0/0 0.0.0.0/0 tcp apt:8080 to:172.0.2:8080

# namespaces
they allow processes to be attached to private ntw segments
these private ntw are bridged into a shared ntw with the rest of containers
containers have virtual ntw "cards"

containers get their own copy of ntw stack