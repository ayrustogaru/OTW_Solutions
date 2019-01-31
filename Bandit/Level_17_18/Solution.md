#### Question:
>There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new 
>and is the only line that has been changed between passwords.old and passwords.new. NOTE: if you have solved this level and 
>see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19.

#### Solution:
```
diff passwords.new passwords.old
```
Read man page for the `diff` command to know how it works