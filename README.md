# docker-rrsoft-ci
# rrsoft-ci

# Installation
- install [docker](https://docs.docker.com/mac/)
- after successfully setup, run `docker-compose up`
- jenkins will be accessible from [http://192.168.99.100:32783](http://192.168.99.100:32783)
- gitlab will be accessible from [http://192.168.99.100:10080](http://192.168.99.100:10080)

# Running
- add ssh key into your gitlab project (Profile Settings > SSH Keys)
- create a new project in gitlab

# Something to Notice
- after you create the project, it will be in  something similar `ssh://git@192.168.99.100:10022/root/fs.git`, note that the port is `10022` instead of `10080`, and use `192.168.99.100` instead of `localhost`
