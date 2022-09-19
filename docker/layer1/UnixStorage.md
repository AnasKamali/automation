actual storage devices
logical storage devices
filesystems
FUSE filesystems and ntw filesystems


Secret of Docker: COWs

Copy on write
Moving Cows
contents of layers are moved btw containers in gzip files.
container are indepedent of storage engine
any container can load on any storage sys

Volumes and Bind Mounting

Linux VFS (virtual file system)
Mounting devices on VFS
mounting directory in VFS
docker run -ti --rm --priviledge=true ubuntu bash
mkdir example
cd example
mkdir workd
cd
touch a b c d
cd other 
touch other a other b

ls -R
mount -o bind other work
ls-R
unmount work
ls-R
