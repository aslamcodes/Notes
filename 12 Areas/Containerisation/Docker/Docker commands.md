# Images
```shell
docker images
```
# Build a Image from Docker File
```
docker build -t mymicroservice .
```
# Run a Image
```
docker run -it --rm -p 3000:8080 --name mymicroservicecontainer mymicroservice
```
# Stop a docker container
```bash
docker stop container_id
```
#todo