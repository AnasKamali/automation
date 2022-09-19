Start containers and restart when fail
Service Discovey-- allow them to find each other
Resource Allocation -- match containers to computers


# Docker Compose
Singele machine coordination
Design for testing and devlopment
Bring up all your containers, volumes, network etc with one cmd
docker compose up

# Kubernetes
Containers run programs.
Pods group containers together.
Services make pods available to others.
Label are used for very advanced service discovery.
Makes scripting large operation possible with the kubectl cmd
very flixable overlay ntwing
run equally well on your h/w or a cloud provider
built in service discovery

# || EC2 container service(ECS)
task definations~~pods
-define
Tasks 
-runing
Service and exposes it to Net
Connect load balancers (ELBs)