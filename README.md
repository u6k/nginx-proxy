# nginx-proxy

自宅サーバー用のリバース・プロキシーです。

[![CircleCI](https://circleci.com/gh/u6k/nginx-proxy.svg?style=svg)](https://circleci.com/gh/u6k/nginx-proxy)

## Requirement

* Docker
* `$HOME/docker/nginx-proxy/`フォルダ

## Build

`circle.yml`を参照。

## Installation

```
# stop container
$ docker kill nginx-proxy || true
$ docker rm nginx-proxy || true
$ docker kill letsencrypt-nginx-proxy-companion || true
$ docker rm letsencrypt-nginx-proxy-companion || true

# pull image
$ docker pull u6kapps/nginx-proxy
$ docker pull u6kapps/letsencrypt-nginx-proxy-companion

# start container
$ docker run -d \
    --name nginx-proxy \
    --privileged \
    -p 80:80 \
    -p 443:443 \
    -v $HOME/docker/nginx-proxy:/etc/nginx/certs:ro \
    -v /etc/nginx/vhost.d \
    -v /usr/share/nginx/html \
    -v /var/run/docker.sock:/tmp/docker.sock:ro \
    u6kapps/nginx-proxy
$ docker run -d \
    --name letsencrypt-nginx-proxy-companion \
    --privileged \
    -v $HOME/docker/nginx-proxy:/etc/nginx/certs:rw \
    -v /var/run/docker.sock:/var/run/docker.sock:ro \
    --volumes-from nginx-proxy \
    u6kapps/letsencrypt-nginx-proxy-companion
```

## Author

* [os-setup - u6k.Redmine()](https://redmine.u6k.me/projects/os-setup)
* [u6k/nginx-proxy](https://github.com/u6k/nginx-proxy)
* [u6k.Blog()](http://blog.u6k.me/)

## License

* [MIT License](https://github.com/u6k/redmine/blob/master/LICENSE)
