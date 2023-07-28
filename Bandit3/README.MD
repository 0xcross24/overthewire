The password for the next level is stored in a hidden file in the inhere directory.
```
ssh bandit3@bandit.labs.overthewire.org -p 2220

bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -latr
total 12
-rw-r----- 1 bandit4 bandit3   33 Apr 23 18:04 .hidden
drwxr-xr-x 3 root    root    4096 Apr 23 18:04 ..
drwxr-xr-x 2 root    root    4096 Apr 23 18:04 .
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```