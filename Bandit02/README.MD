The password for the next level is stored in a file called spaces in this filename located in the home directory
```
ssh bandit2@bandit.labs.overthewire.org -p 2220

bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat ./spaces\ in\ this\ filename
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ cat "./spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

