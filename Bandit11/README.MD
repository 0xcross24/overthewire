The password for the next level is stored in the file data.txt, which contains base64 encoded data

```
ssh bandit11@bandit.labs.overthewire.org -p 2220

bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

```