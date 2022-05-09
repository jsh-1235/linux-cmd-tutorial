# User

## w (Show who is logged on and what they are doing.)

- w

## who (show who is logged on)

- who

## whoami (print effective userid)

- whoami
- Print the user name associated with the current effective user ID.  Same as id -un.

## id (print real and effective user and group IDs)

- id
- id manager
- id -u manager
- id -gn manager

## su (run a command with substitute user and group ID)

- su - manager

## sudo (execute a command as another user)

- sudo rm -r root

## passwd (change user password)

- sudo passwd -u root (unlock)
- sudo passwd -l root

## usermod (modify a user account)

- sudo usermod -aG sudo manager (add sudoers)
- usermod -u 1001 manager

## groups (print the groups a user is in)

- groups manager

## groupadd (create a new group)

- groupadd bt
- echo $?
- tail /ect/group

## groupdel (delete a group)

- groupdel bt
- echo $?
- tail /ect/group

## gpasswd (administer /etc/group and /etc/gshadow)

- gpasswd -a manager jsh (add)
- gpasswd -d manager jsh (delete)
- groups manager (manager jsh)

## groupmod (modify a group definition on the system)

- groupmod -n group-2 group-1
