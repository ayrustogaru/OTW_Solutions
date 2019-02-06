#### Question:
>There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port 
>you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password
>in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

#### Solution:
For this level we need to supply the password to the setuid binary and listen to it in order to get the password for next level. Fire up a
terminal and run this command.
```
cat /etc/bandit_pass/bandit20 | nc -l -p port-number
```
Open another instance of the terminal and run the `suconnect` binary with port number used above, `port-number`.
```
./suconnect port-number
```
