Websocket
====

## Tools

### [websocketd](https://github.com/joewalnes/websocketd)

Pros: 

- Very easy to establish a single server-client connection.
- Cross platform af
- UNIX philosophy - do one thing and do it well.
- Can be combined with wide variety of tech.
- Github issue page is well maintained.

Cons:
- Does very little - much harder to use once it's more than single server-client. Have to combine with more tech at that point - which gets complicated.

### NGINX WebSocket Reverse Proxy

NGINX can be used to handle SSL, and turns WS into WSS. Example config:

```bash
http {
    include       mime.types;
    default_type  application/octet-stream;
    map $http_upgrade $connection_upgrade {
        default upgrade;
        '' close;
    }
    upstream websocket {
        # You need to run a WS server, and set it as an upstream like this
        server localhost:5000;
    }
    server {
        listen 443 ssl;
        server_name example.com;

        ssl_certificate      ssl_certs/fullchain.pem;
        ssl_certificate_key  ssl_certs/privkey.pem;

        location /websocket {
            # Pass connections to https://example.com/websocket to the internal WS server
            proxy_pass http://websocket;
            proxy_http_version 1.1;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection $connection_upgrade;
            # If no data gets exchanged, socket would timeout. default timeout is 60s.
            proxy_connect_timeout 1d;
            proxy_send_timeout 1d;
            proxy_read_timeout 1d;
        }
    }
}

```