# DDK_Docker
To introduce how to setup Ubuntu xx.04 by docker on localhost.

# Environments
```sh
cat /etc/lsb-release

DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=20.04
DISTRIB_CODENAME=focal
DISTRIB_DESCRIPTION="Ubuntu 20.04.3 LTS"
```

# Why do we use docker?
... </br>

# Let us get started
The subsequent commnads are from "https://docs.docker.com/engine/install/ubuntu/"; thus, for more details, please refer to the website.</br>
### Set up the repository
```sh
sudo apt-get remove docker docker-engine docker.io containerd runc

sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
    
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Install Docker Engine
```sh
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

```sh
docker --version

Docker version 20.10.21, build baeda1f
```

### Check if installed successfully
```sh
sudo docker run hello-world
```
![image](https://user-images.githubusercontent.com/67073582/205501874-e50a9046-5bd1-40b2-835b-fa0b7685aaef.png) </br>
Then we know, "run" includes download if we do not have that image.</br>
We alos observe "image:version" that we will use later. </br>

```sh
sudo docker ps -a
```
![image](https://user-images.githubusercontent.com/67073582/205502110-6fd14c65-1a6e-4e4a-9b10-8ce70e3ff39d.png)

### Download image of Ubuntu 18.04
```sh
docker search ubuntu
docker pull ubuntu:18.04
```
![image](https://user-images.githubusercontent.com/67073582/205502625-3a1af668-c7c4-4943-83eb-1061c969b1d8.png)
```sh
docker images
```
![image](https://user-images.githubusercontent.com/67073582/205502679-0563f55a-a377-4bab-b105-04d9b1539373.png)

### Run container of Ubuntu 18.04
```sh
docker run -it --name=DDK_name --hostname=DDK_hostname -v /tmp/:/tmp/ ubuntu:18.04 /bin/bash
```
![image](https://user-images.githubusercontent.com/67073582/205502986-87337433-2c05-4c11-9264-0951eb570614.png)

### Leave container of Ubuntu 18.04
![image](https://user-images.githubusercontent.com/67073582/205503125-db3e12b3-697c-48b2-80d8-cafde541b046.png)

![image](https://user-images.githubusercontent.com/67073582/205503517-23f5217e-6023-43b2-81ab-bd96408accb6.png)

### Let us start and run it again
![image](https://user-images.githubusercontent.com/67073582/205504068-4a30bf84-330b-49a9-89e2-8ad61a6227bc.png)
![image](https://user-images.githubusercontent.com/67073582/205504091-266c29c1-e9e9-4d2a-b5d9-5002742456c1.png)
```sh
docker exec -it DDK_name /bin/bash
```

# References
1. https://docs.docker.com/engine/install/ubuntu/
2. https://hub.docker.com/_/ubuntu
3. ...
