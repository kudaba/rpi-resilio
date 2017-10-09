Docker script for Resilio on Raspberry PI

Used for Docker Image on [DockerHub](https://hub.docker.com/r/kudaba/rpi-resilio/)

To Update:

docker build -t kudaba/rpi-resilio:<version> .  
docker tag kudaba/rpi-resilio:<version> kudaba/rpi-resilio:latest  
docker push kudaba/rpi-resilio  

To Restart:
  
docker stop resilio  
docker rm resilio  
docker run --restart=always -d \
 -p 8888:8888 -p 55555:55555\
 -v /etc/localtime:/etc/localtime:ro \
 -v /drive/PI/config/rslsync:/opt/rslsync/etc -v /drive:/drive \
 --name resilio kudaba/rpi-resilio
