jenkins-docker-arm
==================

Ansible playbook to configure a docker-enabled raspberry pi to rebuild Jenkins images for Raspbian / ARM 
and push them to **my** dockerhub repo [gfouquet/jenkins]()

What does the playbook do ?
---------------------------
1. install a build script and an appropriate Dockerfile
2. set some folders
3. cron the build script (every 3 hours)


What does the build script do ?
-------------------------------
1. checkout the official [jenkins/docker]() repository
2. add a patched Dockerfile to it
3. add a patched publish.sh script
4. run the patched publish.sh script

The edited version of publish.sh will build the 10-ish latest jenkins images 
and push them to the [gfouquet/jenkins]() dockerhub public repo 

[jenkins/docker]: https://github.com/jenkinsci/docker
[gfouquet/jenkins]: https://hub.docker.com/r/gfouquet/jenkins/