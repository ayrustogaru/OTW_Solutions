#### Question:
>The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc 
>to log you out when you log in with SSH.

#### Solution:
```
ssh bandit18@bandit.labs.overthewire.org -p2220 cat readme
```
Enter the password obtained from level 17.
