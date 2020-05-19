# Solve "invalid token"
When I use postfixadmin, I encounter this trouble:
```
invalid token (session timeout; refresh the page and try again?)
```
that means the `session` is not work.

## How to slove it
Because I use nginx with php, so I need to give nginx permission to read/write/excute. so do these:
```
sudo setfacl -R -m u:nginx:rwx /var/lib/php/opcache/ /var/lib/php/session/ /var/lib/php/wsdlcache/
```
