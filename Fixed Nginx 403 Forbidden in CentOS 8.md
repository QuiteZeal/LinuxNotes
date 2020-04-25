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
and then, it works.
