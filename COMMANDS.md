| Commands | Used Area|
| --- | --- |
| **`ssh-keygen`** | to create to key pair (as a default it is id_rsa) |
| **`ssh-keygen -t ed25519 -C <comment>`** | to create specific type of key like `ed25519` |
| **`ssh-agent /bin/bash`** | to run ssh agent |
| **`semanage port -a -t ssh_port_t -p tcp <port number>`** | to add new port for ssh that we defined in `/etc/ssh/sshd_config` file |
|**`semanage port -l | grep <port number>`** | to look for specific port which allowed by Selinux |
|**`scp -P <port number> <source> <destination>`**  Ex: *scp -P 4222 /etc/hosts  user@192.168.134.99:/tmp/* | to copy folder/files to dremote server using `scp`|
|**`rsync -vz -e "ssh -p 4222" source destination`** <br><hr>  `-v` verbouse <br><hr> `-z` compress file data during the transfer <br><hr> `-e` to run shell commands in remote machine| to copy iles/folder to a remote server using `rsync` | 
| **`/etc/hosts.allow`**  | to allow specific hosts to do antything in server like log in via ssh <br><hr> `sshd: 192.168.100.120` <br><hr>`sshd: 192.168.100.100: deny` |
| **`/etc/hosts.deny`**  | This file contains access rules which are used to deny connections to network services (The rules in this file can also be set up in `/etc/hosts.allow` with a 'deny' option instead.) (`sshd: 192.168.100.100`) | 
| **`tcpdmatch sshd <ip address>`** | to check syntax of `/etc/hosts.allow` and `/etc/hosts.deny` files|


