#### Problem:
>The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
>human-readable, 1033 bytes in size and not executable.

#### Solution:
Assuming human readable corresponds to ASCII format, we can write a line of code as follows using the `file`, `find` and `grep`:
```
find -type f -size 1033c ! -executable -exec file {} \; | grep ASCII
```
Voila! you found the file, just `cat` it out.
