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
- tail /etc/group | awk -F: '{print $1}'
- tail /etc/gshadow (그룹 암호 설정 정보을 갖고 있다.)

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
- gpasswd -A admin group (그룹 관리자 추가)
- gpasswd -a user group(그룹 멤버 추가)
- gpasswd -d user group(그룹 멤버 삭제)
- gpasswd -M user group(그룹 멤버 변경)

## groupmod (modify a group definition on the system)

- groupmod -n group-2 group-1 (그룹 1을 그룹 2로 변경)
