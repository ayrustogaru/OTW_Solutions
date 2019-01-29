#### Question:
>The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the 
>range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL 
>and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you 
>send to it.

#### Solution:
```
nmap -sV -vv -p 31000-32000 localhost
```
The output would be two SSL services on localhost and their respective ports. `-sV` will probe open ports to determine service/version 
info.`-vv` turns on the verbose mode.
```
cat etc/bandit_pass/bandit16 | openssl s_client -connect localhost:31790
```
You get the RSA private key for the next level, copy it.
```
mkdir /tmp/keyz/sshkey
cat >/tmp/keyz/sshkey
```
Paste it into the file. We have to change permissions for the file. `ssh` doesn't accept files that are too open.
```
chmod 600 /tmp/keyz/sshkey
ssh -i /tmp/keyz/sshkey bandit17@localhost
```
