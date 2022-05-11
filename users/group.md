# group

## Group list

- cat /etc/group
- cat /etc/group | grep bt
- grep bt /etc/group

## groups (print the groups a user is in)

- groups
- groups root
- groups manager
- tail /etc/group | awk -F: '{print $1}'
- tail /etc/gshadow (그룹 암호 설정 정보을 갖고 있다.)

## groupadd (create a new group)

- groupadd bt
- echo $?
- tail /etc/group

## groupdel (delete a group)

- groupdel bt
- echo $?
- tail /etc/group

## gpasswd (administer /etc/group and /etc/gshadow)

- gpasswd -a group user (add)
- gpasswd -d group user (delete)
- groups manager (manager jsh)

## groupmod (modify a group definition on the system)

- groupmod -n group-2 group-1

## getent (get entries from Name Service Switch libraries)

- getemt passwd
- getemt passwd | grep jsh
- getemt passwd | grep jsh | cut -f1 -d:
- getemt passwd | grep jsh | cut -f2 -d:
- getent passwd | awk -F: '{print $1}'
