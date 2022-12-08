# Docker WS Videostream Proxy

* [Companion repository for the HTML Client](https://github.com/mpolinowski/html_ws_client)


This NGINX proxy brokers a websocket connection between a web client and your local camera. Select the server configuration file you want to use (plain or TLS) in `nginx.conf` and add your cameras and your servers IP or domain to the selected configuration file inside `conf.d`.

__Note__: The repository contains a self signed TLS certificate. This can be used for testing - e.g. with a tool like `wscat`. But your browser is going to reject it. You will have to provide a valid CA signed certificate (e.g. Let's Encrypt) to use the secure websocket variant:


```bash
WebSocket ERROR: {
    "isTrusted": false
}
```

_Run in foreground_

```bash
docker run --rm --network host -v /path/to/docker_ws_video_proxy:/etc/nginx --name proxy nginx:alpine
```

_Run in background_

```bash
docker run --rm --network host -v /path/to/docker_ws_video_proxy:/etc/nginx --name proxy nginx:alpine
```

__Related__:

* [NGINX Websocket Proxy](https://mpolinowski.github.io/docs/DevOps/NGINX/2022-12-08-nginx-websocket-proxy/2022-12-08)
* [Github Repository](https://github.com/mpolinowski/ws-api-proxy)



