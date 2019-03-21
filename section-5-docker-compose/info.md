# Docker compose with multiple local containers

# 51. Docker Compose
1. Docker compose use to automate some of the command to run containers
2. Can be used to start multiple docker containers at the same time

Put it in yml file

# 53. Networking with Docker Compose
Docker compose : automatically create containers on same network, and have free access to communicate each other.

Don't need to setup port

## 57. Automatic Container Restarts

1. "no" : never attempt to restart this. container if it stops or crashes
2. always : if this container stops for any reason, always attempt to restart it 
3. on-failure : only restart if the container stops with an error code (exit code other than 0)
3. unless-stopped : always restart unless the developers forcibly stop it

Service : suatu aplikasi yang berjalan