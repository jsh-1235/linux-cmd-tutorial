# history  (GNU History Library)

- type history
- help history

## view

- history
- history 5

## execution (hash/bang)

- !1
- !2
- !str (str로 시작하는 가장 최근 명령어 실행)

- !! (바로 직전에 사용한 명령어)
- !$ (마지막으로 실행한 명령어의 마지막 인수 표시)
- !-n (현재 이력 번호에서 n번 전의 명령어 실행)

- ^str01^str02 (직전에 실행했던 명령어 중 문자열 str01을 str02로 치환하여 실행한다.)

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

## hash (Remember or display program locations.)

- hash
- hash -r (forget all remembered locations)
- hash -t ls (print the remembered location of each NAME)
