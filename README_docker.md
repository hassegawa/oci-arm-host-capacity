# oracle-tf
### [source and config](https://github.com/hitrov/oci-arm-host-capacity)

* build Dockerfile
  * $ docker login
  * $ docker buildx build --platform linux/arm64,linux/amd64 -t DOCKER/IMAGENAME:IMAGETAG -o type=registry .


* Build DockerfilePerformance, edit DockerfilePerformance to first image
  * $ docker login
  * Fisrt and Second___: docker buildx build --platform linux/arm64,linux/amd64 -f DockerfilePerformance -t DOCKER/IMAGENAME:IMAGETAG -o type=image .  
  * Thirt______________: docker buildx build --platform linux/arm64,linux/amd64 -f DockerfilePerformance -t DOCKER/IMAGENAME:IMAGETAG -o type=registry . 

* run
  * $ docker create --name machine DOCKER/IMAGENAME:IMAGETAG
  * $ docker cp your-private-file.pem machine:/app/oci-arm-host-capacity 
  * $ docker cp .env machine:/app/oci-arm-host-capacity 
  * $ docker start machine
