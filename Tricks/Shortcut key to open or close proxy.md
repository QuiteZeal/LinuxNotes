# Shortcut key to open or close proxy
Suppose you want to create a shortcut key to turn on or off the proxy, you can do these:

## Use bash
Edit you .bashrc,of course, you can also do it on zsh, and then appendf following:
```
# Shortcut
alias proxy-on="export http_proxy='http://127.0.0.1:1080'; export https_proxy=$http_proxy"
alias proxy-off="unset http_proxy; unset https_proxy"
```
and restart your bash or zsh.

So next time, you can turn on and off by proxy-on and proxy-off.
