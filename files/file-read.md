# File Read

## cat (concatenate files and print on the standard output)

- cat FILE
- cat < FILE
- cat -n FILE
- cat -b FILE (빈줄은 번호를 표시하지 않는다.)
- cat -A FILE (모든 제어 문자를 표시한다.)
- cat > FILE (Output Redirection)
- cat >> FILE (Append)

## tac (concatenate and print files in reverse)

- tac FILE

## nl (number lines of files)

- nl FILE (cat -b FILE)
- nl FILE1 FILE2 FILE3
- nl FILE | more

- nl -w1 FILE
- nl -w6 FILE (use NUMBER columns for line numbers)
- nl -w12 FILE

- nl -i2 FILE (line number increment at each line)
- nl -v2 -i2 FILE (first line number for each section)
- nl -v2 -i2 FILE1 > FILE2

## tee (read from standard input and write to standard output and files)

- 표준 입력으로부터 데이터를 읽어 표준 출력으로 출력하거나 또는 이와 동시에 파일에 저장할 수 있다.
- 표준 출력과 파일 저장을 동시에 수생할 수 있기 때문에 파이프라인을 양 갈래로 나누어 보낼 수 있다.

- tee
- Ctrl + D (exit)

- echo "hello" | tee FILE

- ls -al / | tee FILE
- cat FILE1 | tee FILE2

- dpkg -l | tee FILE
- whoami | tee -a FILE (append)
- uname -a | tee -a FILE (append)

## more (file perusal filter for crt viewing)

- more FILE
  - space : next page
  - enter : next line
  - q : exit

- more +10 FILE (display file beginning from line number)
- more -10 FILE (the number of lines per screenful)
- more +/string FILE (display file beginning from search string match)

## less (opposite of more)

- 압축 해제 기능 및 메모리만 절약 기능
- less FILE
- less -N FILE

- less +10 FILE
- less +/string FILE (key : n, b)

## head (file perusal filter for crt viewing)

- head FILE
- head -n 10 FILE (default: 처음부터 10번째줄 까지 표시한다.)
- head -n 10 FILE (head -n +10 FILE, head 10 FILE)
- head -n -10 FILE (뒤의 10줄을 제외하고 모두 보여준다.)
- head -c 100 FILE (100 bytes)

- head -n 5 city number (앞의 다섯줄만 보여준다.)
- head -n 5 city number -q (--quiet: never print headers giving file names)

## tail (file perusal filter for crt viewing)

- tail FILE
- tail -n 10 FILE (default: 끝에서 10번째줄 까지 표시한다.)
- tail -n 10 FILE (tail -n -10 FILE, tail -10 FILE)
- tail -n +10 FILE (앞의 10줄을 제외하고 모두 보여준다.)
- tail -n +5 number city -q (never output headers giving file names)
- tail -c 40 FILE (40 bytes)

- tail -f /var/log/FILE (output appended data as the file grows)