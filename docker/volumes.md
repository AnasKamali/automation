## virtual discs to store and share data
## two main varieties
    1. Persistent -- availabel on host
    2. Ephemeral  -- available as long as being used
# sharing data with the host
    1. Shared folders with the host
    2. sharing a single file
mkdir example
docker run -ti -v /location:/shared-folder ubuntu bash
ls /shared-folder/ 
touch /shared-folder/my-data
## same for file

# Sharing data btw containers
docker run -ti -v /shared-data --name my-f ubuntu bash 
docker run -ti --volume-from my-f --name my-s ubuntu bash
docker run -ti --volume-from my-s --name my-t ubuntu bash
** on exit of all container volume will be lost
