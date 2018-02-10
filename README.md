# Docker-clean_up

### remove stopped docker container
```
docker rm $(docker ps -qa --no-trunc --filter "status=exited")
OR
sudo docker rm $(sudo docker ps -qa --no-trunc --filter "status=exited")
```


### remove stopped docker images
```
docker rmi $(docker images --filter "dangling=true" -q --no-trunc)
OR
sudo docker rmi $(sudo docker images --filter "dangling=true" -q --no-trunc)

docker rmi $(docker images | grep "none" | awk '/ / { print $3 }')
OR
sudo docker rmi $(sudo docker images | grep "none" | awk '/ / { print $3 }')
```
