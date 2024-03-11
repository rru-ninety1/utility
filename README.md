# utility
Utility, documentation...

- [Azure Data Studio](#azure-data-studio)
- [SSH](#ssh)
- [Nuget usefull packages](#nuget-usefull-packages)
- [Mouse without Borders](#mouse-without-borders)


## Azure Data Studio

### Extensions

- Admin Pack for SQL Server
- SQL Server Schema Compare

### Notebooks
- [DBMaintenance](DBMaintenance.ipynb)


<hr>

## SSH

### Tunnel
https://linuxize.com/post/how-to-setup-ssh-tunneling/

#### Access remote port
~~~bash
ssh -L [LOCAL_IP:]LOCAL_PORT:DESTINATION:DESTINATION_PORT [USER@]SSH_SERVER

ssh -L local_port:local_ip_on_remote:local_port_on_remote user@sshserver

ssh -L 0.0.0.0:20011:127.0.0.1:20011 user@public_ip
~~~

#### Expose local port on remote

~~~bash
ssh -R port:local_ip:port -N user@public_ip
~~~

#### Expose local port on remote with `autossh`

Create a systemd service

~~~bash
sudo nano /etc/systemd/system/autossh-tunnel.service
~~~

~~~ini
[Unit]
Description=AutoSSH tunnel
After=network.target

[Service]
Environment="AUTOSSH_GATETIME=0"
User=[user]
RestartSec=15
Restart=always
KillMode=mixed
ExecStart=/usr/bin/autossh -o ServerAliveInterval=30 -o "ServerAliveCountMax 3" -M 0 -o ExitOnForwardFailure=yes -R port:local_ip:port -N user@public_ip

[Install]
WantedBy=multi-user.target
~~~

<hr>

## Nuget usefull packages

### MediatR

### OperationResultTools

### Ardalis.Specification

### Refit.HttpClientFactory

### Yarp.ReverseProxy

### Serilog.AspNetCore

### Serilog.Sinks.File

### prometheus-net.AspNetCore

### NSubstitute

### FluentAssertions

### MockQueryable.NSubstitute

### FluentValidation.DependencyInjectionExtensions


## Mouse without borders

Share mouse and keyboard between Windows pc.
