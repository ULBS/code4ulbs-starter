# Environments

## Staging Environments

| Domain | IP:Port | Service / Description |
| :--- | :--- | :--- |
| `staging.ulbsibiu.ro` | `172.17.102.59:80` | Coolify |
| `staging-app01.ulbsibiu.ro` | `172.17.102.59:3001` | Portainer |
| `staging-app02.ulbsibiu.ro` | `172.17.102.59:3002` | Site DEP CIE |
| `staging-app03.ulbsibiu.ro` | `172.17.102.59:3003` | Teme Licenta |
| `staging-app04.ulbsibiu.ro` | `172.17.102.59:3004` | Platacuora |
| `staging-app05.ulbsibiu.ro` | `172.17.102.59:3005` | Internships |
| `staging-app06.ulbsibiu.ro` | `172.17.102.59:3006` | Exams |
| `staging-app07.ulbsibiu.ro` | `172.17.102.59:3007` | Schedule |
| `staging-app08.ulbsibiu.ro` | `172.17.102.59:3008` | |
| `staging-app09.ulbsibiu.ro` | `172.17.102.59:3009` | |
| `staging-app10.ulbsibiu.ro` | `172.17.102.59:3010` | |
| `staging-app11.ulbsibiu.ro` | `172.17.102.59:3011` | |
| `staging-app12.ulbsibiu.ro` | `172.17.102.59:3012` | |
| `staging-app13.ulbsibiu.ro` | `172.17.102.59:3013` | |
| `staging-app14.ulbsibiu.ro` | `172.17.102.59:3014` | |
| `staging-app15.ulbsibiu.ro` | `172.17.102.59:3015` | |
| `staging-app16.ulbsibiu.ro` | `172.17.102.59:3016` | |
| `staging-app17.ulbsibiu.ro` | `172.17.102.59:3017` | |
| `staging-app18.ulbsibiu.ro` | `172.17.102.59:3018` | |
| `staging-app19.ulbsibiu.ro` | `172.17.102.59:3019` | |
| `staging-app20.ulbsibiu.ro` | `172.17.102.59:3020` | ULBS Backstage |

On staging.ulbsibiu.ro we have Coolify running. Coolify manages all other staged apps. In order for the app to be accessible, configure it to listen to the specified port (e.g. `staging-app07` should listen on port `3007`)

## System Setup

### User Management
```bash
sudo adduser username
sudo passwd username
sudo usermod -aG wheel username
```

### SSH Key Configuration
Run on local machine:
```bash
ssh-keygen -t ed25519
```
Then copy the content of the `.pub` file to the remote server in `~/.ssh/authorized_keys`.

### Docker Installation
```bash
sudo dnf install -y dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo systemctl start docker
sudo systemctl enable docker
```

### Docker Permissions
Give docker rights to the `build` user:
```bash
sudo usermod -aG docker build
newgrp docker
# then restart the runner service!
```
