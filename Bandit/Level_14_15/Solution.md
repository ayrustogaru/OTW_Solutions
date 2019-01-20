#### Question:
> The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

#### Solution:
```
cat /etc/bandit_pass/bandit14 | nc localhost 30000
```
