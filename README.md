# Docker Setup
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

## Docker Desktop

### Download and install Docker Desktop https://docs.docker.com/desktop/setup/install/
- Launch Docker Desktop
  
![image](https://github.com/user-attachments/assets/ed57f40e-29b3-465d-a767-8c1ac17b933e)

- Select Personal
- Skip register
- Skip survey
  
![image](https://github.com/user-attachments/assets/776a1e43-32ec-4a2a-a059-fdb11904f34a)

Select the Terminal word in the bottom right corner to bring up the terminal console.
In the terminal window, run the following commands.
```
$ docker run -dit ubuntu:24.10
```
In the terminal window, connect to the container.
```
$ docker exec -it c3bb16d4860e43a71ee91d5782cc404fa9809bb76e70e4d9f5144c972ef37cef /bin/bash
```

![image](https://github.com/user-attachments/assets/9b18b941-a334-4440-9987-0e6a5208b4bf)


In the terminal window, create a user
```
# apt update
# apt install sudo
# apt install nano
# useradd -m -s /bin/bash lawrence
# passwd lawrence
# usermod -aG sudo lawrence
# su - lawrence
$ whoami
lawrence
$ sudo whoami
[sudo] password for lawrence: 
root
$ exit
```

