The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable


ssh bandit5@bandit.labs.overthewire.org -p 2220

bandit5@bandit:~/inhere$ ls
maybehere00  maybehere02  maybehere04  maybehere06  maybehere08  maybehere10  maybehere12  maybehere14  maybehere16  maybehere18
maybehere01  maybehere03  maybehere05  maybehere07  maybehere09  maybehere11  maybehere13  maybehere15  maybehere17  maybehere19
bandit5@bandit:~/inhere$ find ./* -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ ls -altr ./maybehere07/.file2
-rw-r----- 1 root bandit5 1033 Apr 23 18:04 ./maybehere07/.file2
bandit5@bandit:~/inhere$ find ./* -size 1033c -type f ! -executable
./maybehere07/.file2
bandit5@bandit:~/inhere$ find ./* -type f -size 1033c ! -executable exec file {} | grep ASCII
find: paths must precede expression: `exec'
bandit5@bandit:~/inhere$ find ./* -type f -size 1033c ! -executable file {} | grep ASCII
find: paths must precede expression: `file'
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable -exec file {} + | grep ASCII
./maybehere07/.file2: ASCII text, with very long lines (1000)
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU