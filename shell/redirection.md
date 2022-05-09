# Redirection

## Communication Channels

- stdin (0) : Keyboard (0<, 0<<) - 표준 입력
- stdout (1) : Terminal (1>, 1>>) - 표준 출력
- stderr (2) : Terminal (2>, 2>>) - 표준 에러 출력

## /dev/null

- trash can

## stdout 1

- date > date.txt
- ls date.txt
- ls date.txt 2> error.txt
- cat *

## stdout 2

- touch file{1..3}
- ls file1 file4 2> /dev/null

## stdout 3

- ls -al /etc > result.txt
- ls -al /etc > result.txt 2> error.log

## stdout (head)

- head -n 5 result.txt > result2.txt (Redirects the output of the head command (detailed above) to a file "new_file")
- head -n 10 some_file >> exist_file

## mailx

- sudo mailx -s "Test Mail" bt1@localhost
- ctrl+d
- sudo mailx -s "Test Mail" bt1@localhost < message.txt
- mailx
