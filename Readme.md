# Docker images

Dockerized HTTP servers

## Howto

### Build image
`docker build -t myimage dir`

### Run container
`docker run -d -p 8080:8080 myimage`

### Test service
`curl localhost:8080`
