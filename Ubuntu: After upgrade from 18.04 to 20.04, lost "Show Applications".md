# Ubuntu: After upgrade from 18.04 to 20.04, lost "Show Applications"
The key is:
I upgrade use command line, and meantime I use a lot of `gnome-extension`.

However, the extension maybe can't meet the new system version. So, we need to clear them.

## Clear them by force way
If you just close them or update them on `extensions.gnome.org`, it still not works.

**I choose to delete them manually, and re-install.**

And the directory is:
```
~/.local/share/gnome-shell/extensions
```
