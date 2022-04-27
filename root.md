# root

## change passwd

- sudo passwd root
- [sudo] password for jsh:
- New password:
- Retype new password:
- passwd: password updated successfully

## change user

- su

## user list

- cat /etc/passwd
- cut -f1 -d: /etc/passwd
- grep /bin/bash /etc/passwd (useradd)
- grep /bin/bash /etc/passwd | cut -f1 -d:
