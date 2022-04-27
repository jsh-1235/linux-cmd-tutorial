# User

## w

- w - Show who is logged on and what they are doing.

## who

- who - show who is logged on

## whoami

- whoami - print effective userid
- Print the user name associated with the current effective user ID.  Same as id -un.

## id

- id - print real and effective user and group IDs

## root user

- passwd (비밀번호 재설정)

## su (Super User or Root User)

- su - run a command with substitute user and group ID
- su
- su passwd
- exit
- sudo passwd -u root (unlock)
- sudo passwd -l root
- su - root
- sudo usermod -a -G sudo manager

## adduser & userdel

- adduser manager
- userdel manager
- su - manager
- sudo pwd
- logout (exit)

## userdel

- useradd manager
- useradd manager -d /home/manager_dir
- passwd manager
- su - manager
- su --login manager
- sudo pwd
- logout (exit)

## groups

- groups manager

## Changing file permissions and attributes

- chmod 777 filename
- rwx:rwx:rwx [User/Grop/Others] => [u/g/o]
- rwx [Read/Write/Execute]

