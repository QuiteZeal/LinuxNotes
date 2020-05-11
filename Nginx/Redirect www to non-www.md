# Redirect www to non-www
## The Problem
At the begin, I direct use:
```
server {
    listen       80;
    server_name  ahaknow.com www.ahaknow.com;
    ...
}
```
after I use SSL, I got not security when visiting one of them.
**Because I didn't make different when I use certbot to add SSL.

## The Solution
I should do is let www direct to non-www, and let non-www works separately.
So, I change to this:
```
server {
    listen       80;
    server_name  www.ahaknow.com;
    return       301 $scheme://ahaknow.com$request_uri;
}

server {
	  listen       80;
    server_name  ahaknow.com;
    
    ...

}
```
>tip: $scheme will get the http protocol.
