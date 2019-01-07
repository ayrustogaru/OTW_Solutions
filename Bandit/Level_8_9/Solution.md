#### Problem:
>The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

#### Solution:
```
sort data.txt | uniq -u
```
The `-u` option in `uniq` command will print the only the unique lines in the text file on to the output
