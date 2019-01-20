#### Question:
> The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost
> using SSL encryption.

#### Solution:
``` 
openssl s_client -connenct localhost:30001
```
then type in the password for level 15.
