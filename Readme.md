#Build python container

```
docker build -t demo-python -f Docker-python ./
docker run -it --rm --name demo-python -p 8001:8001 demo-python
```

# Build go container

```
# statically linked
docker run --rm -v "$PWD":/usr/src/demo -w /usr/src/demo golang:1.10 bash -c 'go get ./... ; CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -v'
docker build -t demo-go -f Docker-go ./
docker run -it --rm --name demo-go -p 8080:8080 demo-go
```
