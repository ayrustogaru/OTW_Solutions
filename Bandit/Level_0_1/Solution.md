#### Question:
>The password for the next level is stored in a file called - located in the home directory

#### Solution:
When a command sees the string `-` as a filename, it treats it as a synonym for stdin. To get around this, you need to alter 
the string that cat sees in such a way that it still refers to a file called `-`. The usual way of doing this is to prefix the 
filename with a path - `./-`
```
cat ./-
```
