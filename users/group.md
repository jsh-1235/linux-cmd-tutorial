# group

## Group list

- cat /etc/group
- cat /etc/group | grep bt
- grep bt /etc/group

## groups (print the groups a user is in)

- 현재 사용자가 속해 있는 그룹을 확인
- groups
- groups root
- groups manager
- nl /etc/group | awk -F: '{print $1}'
- nl /etc/gshadow (그룹 암호 설정 정보을 갖고 있다.)

- nl /etc/group | grep sudo

## groupadd (create a new group)

- groupadd [-gor] bt
- echo $?
- tail /etc/group

## groupdel (delete a group)

- groupdel bt
- echo $?
- tail /etc/group

## gpasswd (administer /etc/group and /etc/gshadow)

- 사용자 그룹 패스워드 설정, 관리자와 멤버 추가/삭제

- gpasswd group (그릅 패스워드 설정)
- nl /etc/gshadow (Secure group account information.)
- gpasswd -r group (Remove the password from the named group. The group password will be empty.)

- gpasswd -a user group(Add the user to the named group.)
- gpasswd -d user group(Remove the user from the named group.)

- gpasswd -M jsh bt(Set the list of group members.)
- nl /etc/group | grep bt

- gpasswd -A jsh bt(Set the list of administrative users.)
- nl /etc/group | grep bt

## groupmod (modify a group definition on the system)

- groupmod -n group-2 group-1 (그룹 1을 그룹 2로 변경)
