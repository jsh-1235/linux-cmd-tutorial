# ssh

## Level -1

- ssh bandit0@bandit.labs.overthewire.org -p 2220
- bandit0

## Level 0

- ssh bandit1@bandit.labs.overthewire.org -p 2220
- boJ9jbbUNNfktd78OOpsqOltutMc3MY1

## Level 1

- cat ./-
- ssh bandit2@bandit.labs.overthewire.org -p 2220
- CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

## Level 2

- cat "spaces in this filename"
- ssh bandit3@bandit.labs.overthewire.org -p 2220
- UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

## Level 3

- ls -al
- ssh bandit4@bandit.labs.overthewire.org -p 2220
- pIwrPrtPN36QITSp3EQaw936yaFoFgAB

## Level 4

- file -i ./-file0?
- ssh bandit5@bandit.labs.overthewire.org -p 2220
- koReBOKuIDDepwhWk7jZC0RTdopnAYKh

## Level 5

- ls -alFRh | less

- find . -type f -exec ls -l {} \; | grep 1033 | awk '{print $9}'

- find . -type f ! -perm /a+x
- find . -type f ! -perm /a+x -exec ls -l {} \;
- find . -type f ! -perm /a+x -size 1033c -exec ls -l {} \;
- find . -type f ! -perm /a+x -size 1033c -exec ls -l {} \; | awk '{print $9}'
- find . -type f ! -perm /a+x -size 1033c -exec ls -l {} \; | awk '{print $9}' > path; cat path

- file -i ./maybehere07/.file2
- ls -l ./maybehere07/.file2 | cut -d' ' -f 5
- cat ./maybehere07/.file2
- ssh bandit6@bandit.labs.overthewire.org -p 2220
- DXjZPULLxYr17uwoI01bNLQbtFemEgo7

## Level 6

- find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
- ls -l /var/lib/dpkg/info/bandit7.password
- cat /var/lib/dpkg/info/bandit7.password
- ssh bandit7@bandit.labs.overthewire.org -p 2220
- HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

## Level 7

- cat data.txt | grep millionth
- ssh bandit8@bandit.labs.overthewire.org -p 2220
- cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## Level 8

- sort data.txt | uniq -c -u
- ssh bandit9@bandit.labs.overthewire.org -p 2220
- UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

## Level 9

- file -i data.txt
- ls -lh data.txt

- cat data.txt | grep -a "="
- cat data.txt | grep -a -E "={4,}"
- cat data.txt | grep -a "=\{4,\}"

- ssh bandit10@bandit.labs.overthewire.org -p 2220
- truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

## Level 10

- base64 -d data.txt
- ssh bandit11@bandit.labs.overthewire.org -p 2220
- IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

## Level 11

- ROT13
- cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
- ssh bandit12@bandit.labs.overthewire.org -p 2220
- 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

## Level 12

- hexdump -C hi > dump.txt
- xxd dump.txt
- xxd -p -r dump.txt

- xxd -r data.txt > question.gz
- file *
- gunzip question.gz
- mv question question.bz2
- bunzip2 question.bz2
- mv question question.gz
- gunzip question.gz
- file *
- mv question question.tar
- tar -xvf question.tar
- mv data5.bin data5.bin.tar
- tar -xvf data5.bin.tar
- mv data6.bin data6.bin.tar
- tar -xvf data6.bin.tar
- mv data8.bin data8.bin.gz
- unzip dat8.bin.gz
- cat data8.bin

- ssh bandit13@bandit.labs.overthewire.org -p 2220
- 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

## Level 13

- cat /etc/bandit_pass/bandit14
- cat: /etc/bandit_pass/bandit14: Permission denied

- ls -l /etc/bandit_pass/bandit14
- file * (sshkey.private: PEM RSA private key)

- hostname
- nc -zv localhost 22
- vim /etc/hosts

- ssh -i "sshkey.private" bandit14@localhost
- cat /etc/bandit_pass/bandit14

- ssh bandit14@bandit.labs.overthewire.org -p 2220
- 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

## Level 14

- nmap localhost
  - 30000/tcp open  ndmps
  - Network Data Management Protocol
- nc -zv localhost 30000
- nc -l -p 30000 (port open: listen mode, for inbound connects)

- hostname -I
- ip addr show
- ip addr show | grep eth0

- nc localhost 30000
- 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

- ssh bandit15@bandit.labs.overthewire.org -p 2220
- BfMYroe26WYalil77FoDi9qh59eK5xNr

## Level 15

- nmap localhost
- nc -l -p 30001

- openssl
- version
- help
- exit

- openssl s_client -connect 127.0.0.1:30001
- BfMYroe26WYalil77FoDi9qh59eK5xNr

- ssh bandit16@bandit.labs.overthewire.org -p 2220
- cluFn7wTiGryunymYOu4RcffSxQluehd

## Level 16

- port scan

- nmap localhost
- nc -zv localhost

```bash
#!/bin/bash

num=31000
while test $num -le 32000
do
    $(nc -zv 127.0.0.1 $num >> result.txt 2>> error.txt)
    ((num++))
done
```

- cat error.txt | grep open
- localhost [127.0.0.1] 31046 (?) open

- nc -zvn 127.0.0.1 31000-32000

- openssl s_client -connect 127.0.0.1:31790
- cluFn7wTiGryunymYOu4RcffSxQluehd
- RSA private key

- vim key
- Permissions 0644 for 'key' are too open.
- chmod 600 key
- ssh -i "key" bandit17@localhost

- ssh bandit17@bandit.labs.overthewire.org -p 2220
- cat /etc/bandit_pass/bandit17
- xLYVMN9WE5zQ5vHacb0sZEVqbrp7nBTn

## Level 17

- diff passwords.old passwords.new
- diff -q passwords.old passwords.new
- diff -u passwords.old passwords.new
- diff -c passwords.old passwords.new

- cmp passwords.old passwords.new

- ssh bandit18@bandit.labs.overthewire.org -p 2220
- kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

## Level 18

- ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
- kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

- ssh bandit19@bandit.labs.overthewire.org -p 2220
- IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x

## Level 19

- ls -l
- -rwsr-x--- 1 bandit20 bandit19 7296 May  7  2020 bandit20-do
- s:setuid (일시적으로 자신의 id를 변경할 수 있는 파일임을 뜻한다.)

- file bandit20-do

- ./bandit20-do
- Example: ./bandit20-do id
- ./bandit20-do id
  - euid=11020(bandit20)
  - EUID에 저장된 UID에 따라 프로세스의 권한이 결정된다고 한다.

- ./bandit20-do cat /etc/bandit_pass/bandit20
- GbKksEFF4yrVs6il55v6gwY5aVje5f0j

- ssh bandit20@bandit.labs.overthewire.org -p 2220
- GbKksEFF4yrVs6il55v6gwY5aVje5f0j

## Level 20

- ls -l
- file * (ELF)

- nc -l -p 33333
  - GbKksEFF4yrVs6il55v6gwY5aVje5f0j
  - gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
- ./suconnect 33333
  - Read: GbKksEFF4yrVs6il55v6gwY5aVje5f0j
  - Password matches, sending next password

- ssh bandit21@bandit.labs.overthewire.org -p 2220
- gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
