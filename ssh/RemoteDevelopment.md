# Remote Development

## Remote Development using SSH

[Getting Started](https://code.visualstudio.com/docs/remote/ssh)

[SSH-Server Installation](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)

[Troubleshooting](https://code.visualstudio.com/docs/remote/troubleshooting#_installing-a-supported-ssh-client)


## Getting Started
1. Install SSH Server on host 
   1. Open Port 22 in firewall
2. Authorize VS Code to connect

### Authorize
Create keygen
```
ssh-keygen -t rsa -b 4096 -f ~/.ssh/is_rsa-remote-ssh
```
Enter passcode

Setting up exports
```
export USER_AT_HOST="[username]@[i.p.add.ress]"
export PUBKEYPATH="$HOME/.ssh/is_rsa-remote-ssh.pub"
```

SSH Setup
```
ssh $USER_AT_HOST "powershell New-Item -Force -ItemType Directory -Path \"\$HOME\\.ssh\"; Add-Content -Force -Path \"\$HOME\\.ssh\\authorized_keys\" -Value '$(tr -d '\n\r' < "$PUBKEYPATH")'"
```

### Link Home Folder to Local
Intall SSHFS

[Mac Install](https://osxfuse.github.io)

[Inztructions](https://code.visualstudio.com/docs/remote/troubleshooting#_using-sshfs-to-access-files-on-your-remote-host)



#### Links
1. (SSH-Server Installation)[https://docs.microsoft.com/en-us/windows-server/administration/openssh/

