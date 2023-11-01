The password for the next level is stored in the file data.txt, which contains base64 encoded data

```
ssh bandit12@bandit.labs.overthewire.org -p 2220

bandit12@bandit:/tmp/moon$ xxd -rp data.txt > data2.txt
bandit12@bandit:/tmp/moon$ ls
data2.txt  data.txt
bandit12@bandit:/tmp/moon$ file data2.txt
data2.txt: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
bandit12@bandit:/tmp/moon$ gunzip data2.bin
gzip: data2.bin.gz: No such file or directory
bandit12@bandit:/tmp/moon$ ls
data2.txt  data.txt
bandit12@bandit:/tmp/moon$ gunzip data2.txt
gzip: data2.txt: unknown suffix -- ignored
bandit12@bandit:/tmp/moon$ ls
data2.txt  data.txt
bandit12@bandit:/tmp/moon$ mv data2.txt data2.bin
bandit12@bandit:/tmp/moon$ ls
data2.bin  data.txt
bandit12@bandit:/tmp/moon$ file data2.bin
data2.bin: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
bandit12@bandit:/tmp/moon$ gunzip data2.bin
gzip: data2.bin: unknown suffix -- ignored
bandit12@bandit:/tmp/moon$ ls
data2.bin  data.txt
bandit12@bandit:/tmp/moon$ mv data2.bin.gz
mv: missing destination file operand after 'data2.bin.gz'
Try 'mv --help' for more information.
bandit12@bandit:/tmp/moon$ mv data2.bin data2.bin.gz
bandit12@bandit:/tmp/moon$ ls
data2.bin.gz  data.txt
bandit12@bandit:/tmp/moon$ file data2.bin.gz
data2.bin.gz: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
bandit12@bandit:/tmp/moon$ gunzip data2.bin.gz
bandit12@bandit:/tmp/moon$ ls
data2.bin  data.txt
bandit12@bandit:/tmp/moon$ ls
data2.bin  data.txt
bandit12@bandit:/tmp/moon$ file data2.bin
data2.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/moon$ mv data2.bin data2.bin.bz
bandit12@bandit:/tmp/moon$ file data2.bin.bz
data2.bin.bz: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/moon$ man bzip
No manual entry for bzip
bandit12@bandit:/tmp/moon$ ls
data2.bin.bz  data.txt
bandit12@bandit:/tmp/moon$ mv data2.bin.bz data2.bin.bz2
bandit12@bandit:/tmp/moon$ bzip2 -d data2.bin.bz2
bandit12@bandit:/tmp/moon$ ls
data2.bin  data.txt
bandit12@bandit:/tmp/moon$ file data2.bin
data2.bin: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/moon$ mv data2.bin data4.bin.gz
bandit12@bandit:/tmp/moon$ gunzip data4.bin.gz
bandit12@bandit:/tmp/moon$ ls
data4.bin  data.txt
bandit12@bandit:/tmp/moon$ file data4.bin
data4.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/moon$ mv data4.bin data4.bin.tar.gz
bandit12@bandit:/tmp/moon$ ls
data4.bin.tar.gz  data.txt
bandit12@bandit:/tmp/moon$ tar -xf data4.bin.tar.gz
bandit12@bandit:/tmp/moon$ ls
data4.bin.tar.gz  data5.bin  data.txt
bandit12@bandit:/tmp/moon$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/moon$ mv data5.bin.tar.gz
mv: missing destination file operand after 'data5.bin.tar.gz'
Try 'mv --help' for more information.
bandit12@bandit:/tmp/moon$ mv data5.bin data5.bin.tar.gz
bandit12@bandit:/tmp/moon$ ls
data4.bin.tar.gz  data5.bin.tar.gz  data.txt
bandit12@bandit:/tmp/moon$ tar -xf data5.bin.tar.gz
bandit12@bandit:/tmp/moon$ ls
data4.bin.tar.gz  data5.bin.tar.gz  data6.bin  data.txt
bandit12@bandit:/tmp/moon$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/moon$ mv data6.bin data6.bin.bz2
bandit12@bandit:/tmp/moon$ bzip2 -d data6.bin.bz2
bandit12@bandit:/tmp/moon$ ls
data4.bin.tar.gz  data5.bin.tar.gz  data6.bin  data.txt
bandit12@bandit:/tmp/moon$ file data6.bin
data6.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/moon$ mv data6.bin data6.bin.tar.gz
bandit12@bandit:/tmp/moon$ tar -xf data6.bin.tar.gz
bandit12@bandit:/tmp/moon$ ls
data4.bin.tar.gz  data5.bin.tar.gz  data6.bin.tar.gz  data8.bin  data.txt
bandit12@bandit:/tmp/moon$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/moon$ mv data8.bin data8.bin.gz
bandit12@bandit:/tmp/moon$ ls
data4.bin.tar.gz  data5.bin.tar.gz  data6.bin.tar.gz  data8.bin.gz  data.txt
bandit12@bandit:/tmp/moon$ gunzip data8.bin.gz
bandit12@bandit:/tmp/moon$ ls
data4.bin.tar.gz  data5.bin.tar.gz  data6.bin.tar.gz  data8.bin  data.txt
bandit12@bandit:/tmp/moon$ file data8.bin
data8.bin: ASCII text
bandit12@bandit:/tmp/moon$ cat data8.bin
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

```