
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

## Password list

cat /etc/shadow

## Group list

cat /etc/group

## Sudoers list

cat /etc/sudoers

## adduser

- adduser manager

## useradd

- useradd manager
- useradd -m manager (create home directory)
- useradd manager -d /home/manager_dir
- sudo useradd -g users username (특정 그룹 지정)
- passwd manager
- useradd -D

## userdel

- userdel manager
- userdel -f manager
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
