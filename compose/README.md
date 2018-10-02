# Installation

## Prerequisites


  - latest docker version: https://get.docker.com/ (compatible with stage build)
  - docker-compose: https://docs.docker.com/compose/install/#install-compose


git clone the repo
move inside the 'compose' folder
```sh
$ docker-compose up -d
```

That's it!
It will spin up two containers: haproxy and drop-wz
drop-wz is created by cloning a single branch from the main repo and can be used with external tools (i.e. jenkins pipelines)
  - Note1: the app will listen on port 8082
  - Note2: the metrics are listening only on localhost (port 8081)
  - to test: <my_public_IP>:8082/hello

The app will log on journald
the healthcheck is only available for the metrics
for clarifications about efficiency/security features, please ask
### TBD
 - create a container for graphite (which is currently throwing a warning)
