The password for the next level is stored in the file data.txt, which contains base64 encoded data

```
ssh -i .\Bandit16\bandit16.key bandit17@bandit.labs.overthewire.org -p 2220
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```