# Use cron to execute the command by the time
The format as follow:
```
min hour day month year command
```
such as:
```
5 0 * * * command
```
means every day's 00:05 to execute the command.

## How to do it
Edit by `crontab -e`, and save.
