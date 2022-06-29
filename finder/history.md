# history  (GNU History Library)

- type history
- help history

## view

- history
- history 5

## execution

- !1
- !2

## append

- history -a (append history lines from this session to the history file)
- cat .bash_history

## clear

- history -c (delete all)
- history -d 1

- 0>.bash_history (.bash_history 파일 삭제)
- cat .bash_history

## statistics

- history | awk '{a[$2]++}END{for(i in a){print a[i] " " i}}' | sort -rn | head -10