process come from other processes --parent child relationship
when child process exits, return an exit code to its parent
Process Zero is special; called init, the process that starts the rest
In docker container starts with an init process and vanishes when that process exits
docker run -ti --rm --name hello ubuntu bash

docker inspect --format '{{.State.Pid}}' hello
7638
docker run -ti --rm --privileged=true --pid=host ubuntu bash
kill 7638


# resource Limiting
scheduling a CPU time
memory allocation limits
inherited limitation and quotas

