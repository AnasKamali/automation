# Docker Registries

## registries manage and distribut images
## you can run your own, as well
docker search ubuntu

docker pull debian:sid
docker tag debian:sid anakamal/test-image-28:v10.18
docker push anakamal/test-image-28:v10.18
