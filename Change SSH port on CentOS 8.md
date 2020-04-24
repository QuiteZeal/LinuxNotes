# Change SSH port on CentOS 8
The key step is to turn your want listen-port and close the default ssh-port.
For CentOS 8, will use `firewalld`

## Open your want listen-port and close the default
```
sudo semanage port -a -t ssh_port_t -p tcp 3000
sudo firewall-cmd --zone=public --permanent --add-port=30000/tcp
sudo firewall-cmd --zone=public --permanent --remove-service=ssh
```
If firewalld not installed, you can manually install and enable it.
```
sudo yum -y install firewalld
sudo systemctl enable --now firewalld
```
And then, reload it:
```
sudo firewall-cmd --reload
```

## Allow new port on SELinux
It will use semange:
```
semanage port -l | grep ssh
```
it will be answered:
`ssh_port_t                     tcp      3000`

## Verify and restart
Use netstat to confirm:
```
$ netstat -tunl | grep 3000
tcp        0      0 0.0.0.0:3000           0.0.0.0:*               LISTEN     
tcp6       0      0 :::3000                :::*  
```
and finally, restart ssh service:
```
sudo systemctl restart sshd
```

**Now, you can ssh your serve at -p 3000, like:
`ssh root@xxx.xxx.xxx.xxx -p3000`**

