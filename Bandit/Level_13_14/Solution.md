#### Question:
> The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, 
> you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost 
> is a hostname that refers to the machine you are working on.

#### Solution:
As per the `man` page, the `-i` option will use the file from which the identity (private key) for public key authentication is read.
```
ssh -i sshkey.private bandit14@localhost
```