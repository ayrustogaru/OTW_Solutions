#### Question:
> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for 
> the configuration and see what command is being executed.

> NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally 
> made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

#### Solution:
1. Check out what the script does as in previous question:
```
$> cat /etc/cron.d/cronjob_bandit23
```
  Output:
```
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null                                                       
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
```
2. Print out the contents of the shell script:
```
$> cat /usr/bin/cronjob_bandit23
```
  Output:
```
#!/bin/bash                                              
                                                         
myname=$(whoami)                                         
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)                                                     
                                                         
echo "Copying passwordfile /etc/bandit_pass/$myname to /t
mp/$mytarget"                                            
                                                         
cat /etc/bandit_pass/$myname > /tmp/$mytarget
```
3. As we can see, the shell stores the username into $myname and uses md5 hash on the string `I am user ` after appending to $myname at 
the start and delimits it upto space character. The password of the next level is dumped in a file in the `/tmp/` directory with its 
name same as the hash.
```
$> echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
$> cat /tmp/8ca319486bfbbc3663ea0fbe81326349
```
