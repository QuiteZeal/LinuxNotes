# Fixed: Connection error when use explicit Ftp over SSL to vsftpd server
I have install SSL under vsftpd, and I try to use FileZilla to connect it, but I got:
```
response: 220 (vsftpd 3.0.3) 
command: auth tls
```
that means: **No permission**

## Why it?
Maybe Because I use CentOS 8 and firewalld, the default FTP port is 21, but similarly it can't works.
So I tried to change the FTP port.

**And, it works!**

## The key
Because I use firewalld, the port is blocked, I need to open it manually, **not FTP service, but the port.**
