# DDK_Docker
To introduce how to setup Ubuntu xx.04 by docker on localhost.

# Why do we use docker?
... </br>

# Let us get started
The subsequent commnads are from "https://docs.docker.com/engine/install/ubuntu/"; thus, for more detail, please refer to the website.</br>
### Set up the repository
```sh
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

### Check if installed successfully
```sh
sudo docker run hello-world
```

### Download container of Ubuntu 18.04
```sh
...
```

# References
1. https://docs.docker.com/engine/install/ubuntu/
2. https://hub.docker.com/_/ubuntu
3. ...
