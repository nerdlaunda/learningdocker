# Installing docker

## Linux

- ### Ubuntu
#### From Repository
##### 1. Setup Repository
1. Update the apt package index and install packages to allow apt to use a repository over HTTPS:

```bash
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
2. Add Docker’s official GPG key:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
3. Use the following command to set up the stable repository. To add the nightly or test repository, add the word nightly or test (or both) after the word stable in the commands below. Learn about nightly and test channels.

> Note: The `lsb_release -cs` sub-command below returns the name of your Ubuntu distribution, such as xenial. Sometimes, in a distribution like Linux Mint, you might need to change `$(lsb_release -cs)` to your parent Ubuntu distribution. For example, if you are using Linux Mint Tessa, you could use bionic. Docker does not offer any guarantees on untested and unsupported Ubuntu distributions.

```bash
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

##### 2. Install Docker Engine
1. Update the `apt` package index, and install the latest version of Docker Engine and containerd, or go to the next step to install a specific version:
```
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

2. To install a specific version of Docker Engine, list the available versions in the repo, then select and install:
    a. List the versions available in your repo:
    ```bash 
    apt-cache madison docker-ce
    ```    

    b. Install a specific version using the version string from the second column, for example, 5:18.09.1~3-0~ubuntu-xenial. 
    ```bash 
    sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
    ```
3. Verify that Docker Engine is installed correctly by running the hello-world image.
```bash
sudo docker run hello-world
```

#### From deb package
1. Go to [Docker Download](https://download.docker.com/linux/ubuntu/dists/), choose your Ubuntu version, then browse to pool/stable/, choose amd64, armhf, or arm64, and download the .deb file for the Docker Engine version you want to install.
2. Install Docker Engine, changing the path below to the path where you downloaded the Docker package.
```bash
sudo dpkg -i /path/to/package.deb
```

3. Verify that Docker Engine is installed correctly by running the 'hello-world' image.
```bash
sudo docker run hello-world
```


- ### CentOS
  
## Mac

## Windows
