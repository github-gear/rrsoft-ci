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

# SSH Keys
- You will need to copy jenkins id_rsa.pub to gitlab (http://192.168.99.100:10080/profile/keys) to get the permission for the git ssh

# Jenkins configure gitlab
- Go to (Jenkins dashboard > Manage Jenkins > Configure System > Gitlab)
- Fill in
	- Connection name: gitlab
	- Gitlab host url: http://192.168.99.100:10080
	- API token:
		- Kind: Secret text
		- Scope: Global
		- Secret: (Get from gitlab > Profile Settings > Account > Private token)
		- Ignore SSL Certificate errors: true
- Save

# Jenkins configure source code management
- Go to (Jenkins dashboard > Your Project > Configure > Source Code Management > git
- Fill in repository URL, and browser
- Tick Build when a change is pushed to GitLab, and copy the GitLab CI service URL
- Save

# Gitlab webhooks
- Go to (Projects > your_organization/your_repo > Settings > Webhooks). i.e.
http://192.168.99.100:10080/your_organization/your_repo/hooks
- Then paste the service url that you copy from Jenkins (http://192.168.99.100:32782/project/your_project). If you did not copy just now, get it from (Jenkins dashboard > Your Project > Configure > Build Triggers > Build when a change is pushed to GitLab. GitLab CI Service URL: )

