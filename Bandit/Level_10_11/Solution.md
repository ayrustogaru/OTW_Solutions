#### Problem:
>The password for the next level is stored in the file data.txt in one of the few human-readable strings, 
>beginning with several ‘=’ characters.

#### Solution:
```
strings data.txt | grep ====
```

`strings` command can be useful in extracting information from binary files. It prints out the human readable characters onto the output.
