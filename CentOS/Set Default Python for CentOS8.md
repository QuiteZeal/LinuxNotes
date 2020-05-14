# Set Default Python for CentOS8
Normally, if you input python in CentOS 8, you will get `python: command not found`. So, we need to set it manually.

## Install Python
Use `yum` or `dnf` all fine, but you should name python2 or python3.

## Set Python
To set Python3:
```
$ sudo alternatives --set python /usr/bin/python3
```
as same to set Python2:
```
$ sudo alternatives --set python /usr/bin/python2
```
if you want Unset python:
```
$ sudo alternatives --auto python
```
This time, you back to the default, `python: command not found`.
