# Fixed Nginx 403 Forbidden
I encountered this problem on CentOS 8, after I have config site.conf.
I got 403, and I visit the error.log to know the problem is:
```
xxxx is forbidden (13: Permission denied)
```

## The Key to Solve
Because CentOS 8 use SELinux, so need set permissive, like:
```
setenforce permissive
```
and then, it works. **But this operation can not work permanently.**

## Avoid Nginx 403 Permanently
The key is to handle with SELinux.

Use these:
Turn on the `httpd network connect`:
```
 setsebool -P httpd_can_network_connect on
```
And get SELinux enforce:
```
getenforce
```
Then, change the security:

```
chcon -Rt httpd_sys_content_t /your_path
```

