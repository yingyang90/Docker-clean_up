# Docker-clean_up

### Remove stopped docker container
```
docker rm $(docker ps -qa --no-trunc --filter "status=exited")
```


### Remove stopped docker images
```
docker rmi $(docker images --filter "dangling=true" -q --no-trunc)

docker rmi $(docker images | grep "none" | awk '/ / { print $3 }')
```

### Remove Unused Docker Images (causion)
```
docker image prune -a -f
```
