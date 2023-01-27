In `C:\Users\USER_NAME\.ssh`
`ssh-keygen` set name `id_rsa`

**Windows powershell**
```code
ssh-add .\id_rsa
```

**To check GIT ssh connection**
```code 
ssh -T git@github.com
```

**Copy original SSH config**

```code
cp /etc/ssh/sshd_config /etc/ssh/sshd_config-raw
```

**Edit SSH config** 
 
```code
vi /etc/ssh/sshd_config
```

**Basic `sshd_config`**

```text
    Port 2222
    PasswordAuthentication yes
    AllowUsers username
```

**Connect to SSH by password**
```code 
sshpass -p 'P@$$w0rD' -oKexAlgorithms=+diffie-hellman-group1-sha1 user@192.168.0.10 -p2222
```

`-oKexAlgorithms=+diffie-hellman-group1-sha1` - [if you connect to old equipment](http://www.openssh.com/legacy.html)

**Connect to SSH (pub key already on server)**
```code
ssh user@192.168.0.10 -p2222
```

**Passing public key from Windows to Linux server**
```text
type C:\Users\USER_NAME\.ssh\id_rsa.pub | ssh -p2222 user@192.168.0.10 "cat >> /home/user/.ssh/authorized_keys"
```

**[To connect to the target host and upload the SSH user key](https://www.ssh.com/academy/ssh/copy-id#how-ssh-copy-id-works)**
```text
ssh-copy-id -i C:\Users\USER_NAME\.ssh\id_rsa.pub -p2222 user@192.168.0.10
```

**Copy the file using SSH with a password**
```text
sshpass -p 'P@$$w0rD' scp -P 2217 spring-boot-app.jar max@178.214.220.16:/dpiqb
```