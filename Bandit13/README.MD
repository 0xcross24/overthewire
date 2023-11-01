The password for the next level is stored in the file data.txt, which contains base64 encoded data

```
ssh bandit13@bandit.labs.overthewire.org -p 2220

bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ hostname
bandit
bandit13@bandit:~$ ssh -i sshkey.private bandit14@bandit

^C
bandit13@bandit:~$ ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
The authenticity of host '[bandit.labs.overthewire.org]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit13/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit13/.ssh/known_hosts).

```