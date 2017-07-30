# nginx-proxy

自宅サーバー用のリバース・プロキシーです。

[![CircleCI](https://circleci.com/gh/u6k/nginx-proxy.svg?style=svg)](https://circleci.com/gh/u6k/nginx-proxy)

## Requirement

* Docker

```
Client:
 Version:      17.03.1-ce
 API version:  1.27
 Go version:   go1.7.5
 Git commit:   c6d412e
 Built:        Tue Mar 28 00:40:02 2017
 OS/Arch:      windows/amd64

Server:
 Version:      17.04.0-ce
 API version:  1.28 (minimum version 1.12)
 Go version:   go1.7.5
 Git commit:   4845c56
 Built:        Wed Apr  5 18:45:47 2017
 OS/Arch:      linux/amd64
 Experimental: false
```

* `${DOCKER_VOLUMES}/nginx-proxy`フォルダ

## Build

`circle.yml`を参照。

## Installation

`docker-compose.yml`を参照

## Author

* [os-setup - u6k.Redmine()](https://redmine.u6k.me/projects/os-setup)
* [u6k/nginx-proxy](https://github.com/u6k/nginx-proxy)
* [u6k.Blog()](http://blog.u6k.me/)

## License

* [MIT License](https://github.com/u6k/nginx-proxy/blob/master/LICENSE)
