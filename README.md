# server-setup

### Here is my server setup

```
sudo apt-get update ; sudo apt-get install -y vim mosh tmux htop git curl wget unzip zip gcc build-essential make mc docker docker-compose
```

```
adduser www
```

```
sudo adduser www sudo
```

```
exit
```

```
ssh-copy-id www@<server ip>
```

```
ssh www@<server ip>
```

```
sudo nano /etc/ssh/sshd_config
```

Add these lines
```
AllowUsers www
PermitRootLogin no
PasswordAuthentication no
UsePAM no
PubkeyAuthentication yes
ChallengeResponseAuthentication no
```

```
sudo service ssh restart
```

```
sudo groupadd docker
```

```
sudo usermod -aG docker $USER
```

```
newgrp docker
```

```
docker run hello-world
```

```
sudo chmod a+x /usr/bin/docker-compose
```

```
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo gpg --dearmor -o /usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh
```

```
gh auth login
```
