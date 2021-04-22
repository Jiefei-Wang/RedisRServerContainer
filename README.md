The Redis server image is responsible for receiving jobs from user's main R session and storing the results returned by R workers.

The server accept the following environment variable on startup

1. sshPubKey: The ssh public key
2. serverPort: The port used by the redis server to accept the incoming connection(default: 6379)
3. serverPassword: The password of the redis server

## example
Build the server image with
```
docker build -t redis_server_image redis_server_image/.
```
Run the server in the foreground with the following arguments
```
docker run -it --env serverPort=6379 --env serverPassword=123456 -p 6666:6379 redis_server_image
```
