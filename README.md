# port-forward-https
Used to forward HTTPS ports

# usage
The following environment variables need to be defined

1. `REMOTE_HOST` : host you want to forward to
1. `REMOTE_PORT` : port on remote host to forward to

Port 443 inside the container will be forwarded to the remote host and port

- use `-P` to have docker pick a random port on the host to forward
- use `-p <host port>:443` to define a custom port to forward where `host port` is the port on the host that needs to be forwarded

# example
The following will forward local host traffic from port 8443 to remote host 10.27.1.2 and port 10443

```
docker run -e REMOTE_HOST=10.27.1.2 -e REMOTE_PORT=10443 -p 8443:443 port-forward
```
