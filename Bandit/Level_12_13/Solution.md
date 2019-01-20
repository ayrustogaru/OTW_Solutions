#### Question
> The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. 
> For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. 
> Then copy the datafile using cp, and rename it using mv (read the manpages!)

#### Solution
```
mkdir /tmp/myname123
cp data.txt /tmp/myname123
xxd -r data.txt data1
file data1
data2: gzip compressed data, was "data2.bin", from Unix, max compression
mv data1 data1.gz
gzip -d data1.gz
file data
data: bzip2 compressed data, block size = 900k
bzip2 -d data2
bzip2: Can't guess original name for data -- using data.out
file data2.out           
data2.out: gzip compressed data, was "data4.bin", max compression, from Unix
mv data2.out data.gz
gzip -d data2.gz
file data2               
data2: POSIX tar archive (GNU)
tar -xf data2
```
and so on, until you get the file **data8** 
```
cat data8
```
 
