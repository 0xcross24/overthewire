The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

```
ssh bandit9@bandit.labs.overthewire.org -p 2220

bandit9@bandit:~$ strings data.txt | grep "==="
4========== the#
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```