
# account

## User list

- ls -al /home
- cat /etc/passwd
- cut -f1 -d: /etc/passwd
- grep /bin/bash /etc/passwd (adduser)
- grep /bin/bash /etc/passwd | cut -f1 -d:
- grep /bin/bash /etc/passwd | cut -d: -f 1 | wc -l
- tail -n 3 /etc/passwd
- grep manager /etc/passwd (Check Login Shell)
- jsh:x:1000:1000:,,,:/home/jsh:/bin/bash

## Password list

- sudo cat /etc/shadow
- jsh:$6$EkLmaqtlJTzlBHPE$9w1s4Q0sXQLVcP/WJWGaln2R2l5umMckcmIW8CWaJ68zgJe/ehOvk24hcshWacetKNexd1cH4bljkC/uRJ5R10:19122:0:99999:7:::

## Group list

- cat /etc/group

## Sudoers list

- sudo cat /etc/sudoers
- su -
- visudo

## adduser

- adduser manager

## useradd

- useradd [-mcdefP] manager
- useradd -m manager (create home directory)
- useradd manager -d /home/manager_dir
- sudo useradd -g users username (특정 그룹 지정)
- useradd -e 2022-12-30 -m user
- passwd manager
- chsh 

## userdel (delete a user account and related files)

- userdel manager
- userdel -f manager
- userdel -r manager (사용자 홈디렉토리도 함께 삭제한다.)
- sudo userdel -r manager

## login (begin session on the system)

- login
- su - manager
- su --login manager
- exit (logout)
- logout

## passwd  (change user password)

- sudo passwd root
- passwd manger

## usermod (modify a user account)

- sudo usermod -aG sudo manager (add sudoers)
- usermod -u 1001 manager

## last (show a listing of last logged in users)

- last
- last jsh
- sudo find /var -name wtmp
- sudo cat /var/log/wtmp
- touch /var/log/wtmp