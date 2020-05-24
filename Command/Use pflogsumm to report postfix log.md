#Use pflogsumm to report postfix log
I want to get postfix log report via mail, so I can use `pflogsumm` and corn.

## How to use it
On CentOS:
```
sudo dnf install postfix-perl-scripts
```

and create a corn
```
sudo crontab -e
```
add:
```
0 1 * * * /usr/sbin/pflogsumm -d yesterday /var/log/maillog --problems-first --rej-add-from --verbose-msg-detail -q
MAILTO:"youremail"
```
That means I can get yesterday postfix report at every day's 1 o'clock.
- `--problems-first` to emit "problem" reports, include bounces, defers, warnings, rejects.
- `--rej-add-from --verbose-msg-detail` to show reject report and reason.
