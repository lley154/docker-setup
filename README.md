# Docker Install
## Linux OS
### Add Docker's official GPG key:
```
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

### Add the repository to Apt sources:
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

### Create data directory (use your preferred path) using Linux shell window
```
sudo mkdir -p /home/your-username/docker-data
```
Set permissions to allow read/write from inside the container
```
sudo chmod -R a+rwx /home/your-username/docker-data/
```
## Mac OS

- Go to https://docs.docker.com/desktop/setup/install/mac-install/ and download the correct version of Docker Desktop

- Double-click Docker.dmg to open the installer, then drag the Docker icon to the Applications folder. By default, Docker Desktop is installed at /Applications/Docker.app.

- Double-click Docker.app in the Applications folder to start Docker.
- Select recommended installation
- If prompted, install Rosetta to enable Intel-based features
- Allow docker to find services on local networks

### Create data directory (use your preferred path) using Mac OS Terminal shell window
```
sudo mkdir -p /Users/your-username/docker-data
```
Set permissions to allow read/write from inside the container
```
sudo chmod -R a+rwx /Users/your-username/docker-data/
```

## Windows OS

https://docs.docker.com/desktop/setup/install/windows-install/

- Download the installer using the download button at the top of the page, or from the release notes.

- Double-click Docker Desktop Installer.exe to run the installer. By default, Docker Desktop is installed at C:\Program Files\Docker\Docker.

- When prompted, ensure the Use WSL 2 instead of Hyper-V option on the Configuration page is selected or not depending on your choice of backend.

- If your system only supports one of the two options, you won't be able to select which backend to use.

- Follow the instructions on the installation wizard to authorize the installer and proceed with the install.

- When the installation is successful, select Close to complete the installation process.

### Create data directory (use your preferred path) using Window shell window
```
mkdir C:\Users\your-username\docker-data
```


# Docker Desktop Setup

https://docs.docker.com/desktop/setup/install/

- Launch Docker Desktop
  
![image](https://github.com/user-attachments/assets/ed57f40e-29b3-465d-a767-8c1ac17b933e)

- Select Personal
- Skip register
- Skip survey
  
![image](https://github.com/user-attachments/assets/776a1e43-32ec-4a2a-a059-fdb11904f34a)

Select the Terminal word in the bottom right corner to bring up the terminal console.
In the terminal window, run the following commands.

#### For Linux OS
```
$ docker run -ditv /home/your-username/docker-data:/data -p 18333:18333 ubuntu:24.10
```

#### For Mac OS
```
$ docker run -ditv /Users/your-username/docker-data:/data -p 18333:18333 ubuntu:24.10
```

#### For Window OS
```
$ docker run -ditv C:\Users\your-username\docker-data:/data -p 18333:18333 ubuntu:24.10
```


## In the terminal window, connect to the container.
```
$ docker exec -it c3bb16d4860e43a71ee91d5782cc404fa9809bb76e70e4d9f5144c972ef37cef /bin/bash
```

![image](https://github.com/user-attachments/assets/9b18b941-a334-4440-9987-0e6a5208b4bf)


In the terminal window, create a user
```
# apt update
# apt install sudo
# apt install nano
# useradd -m -s /bin/bash ubuntu-username
# passwd ubuntu-username
# usermod -aG sudo ubuntu-username
# su - ubuntu-username
$ whoami
ubuntu-username
$ sudo ubuntu-username
[sudo] password for ubuntu-username: 
root
$ sudo chown ubuntu-username /data
$ sudo chgrp ubuntu-username /data
```

