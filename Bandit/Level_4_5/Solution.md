#### Problem:
> The password for the next level is stored in the only human-readable file in the inhere directory.

#### Solution
1. Checking all the file in the inhere directory using the `file` command, only `-file07` had ASCII text in it.

```
$ cd inhere/
$ file ./-file07
```
Output:
```
./-file07: ASCII text
```
2. `cat` the file.
```
$ cat ./-file07
```
