#### Question:
> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ 
> for the configuration and see what command is being executed.

#### Hint:
Study about `cron` from man pages and wikipedia.

#### Solution:
1. List out the files in `/etc/cron.d/`
```
ls /etc/cron.d/
```
2. The output would be three files as follows:
```
cronjob_bandit22  cronjob_bandit23  cronjob_bandit24
```
3. Print out cronjob_bandit22 in order to check what program is running
```
cat cronjob_bandit22
```
4. The output would be as follows:
```
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null                                                        
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
```
5. check out the `/usr/bin/cronjob_bandit22.sh` file
```
cat /usr/bin/cronjob_bandit22.sh
```
6. The contents of this shell script are:
```
#!/bin/bash                                              
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv          
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```
7. As we can see the script is dumping the password in the tmp file, so print out the contents of the tmp file
```
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```
