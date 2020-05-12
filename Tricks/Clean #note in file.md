# A nice method to clear note in file
Sometimes, a file will have lots of notes to tell you how to do. This time, we may prefer to need a concise one file.
## Copy and Pates
Just do this two stpes:
```
mv /yourfile /yourfile.bak
grep -v ^# /yourfile.bak > /yourfile
```
