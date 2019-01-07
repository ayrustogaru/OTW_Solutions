#### Problem:
>The password for the next level is stored somewhere on the server and has all of the following properties:
>owned by user bandit7, owned by group bandit6 and 33 bytes in size

#### Solution:
```
find / -type f -size 33c -group bandit6 -user bandit7 | grep bandit7
```
Change the directory and `cat`
