# File Create

- 파일의 이름은 사용자가 LINUX 시스템의 파일을 접근하고 제어하는데 사용된다.
- I-NODE
  - 파일을 기술하는 디스크 상의 데이터 구조로서 파일의 데이터를 블록이 디스크 상의 어디에 위치하고 있는가와 같은 파일의 중요한 정보를 가지고 있기 때문에 파일에 대한 정보를 기록하기 위해 사용된다.
  - 각각의 파티션마다 0부터 시작하는 정수의 형태를 가지게 되며, 모든 파티션마다 0부터 시작하며, 각기 다른 파티션이면 동일한 I-Node를 가질 수 있다.
  - I-Node는 I-번호라고 하는 고유 식별 번호를 가지고 있으며, I-Node의 숫자는 파일 시스템이 갖고 있을 수 있는 최대 파일의 수가 된다.

- ls -i (파일의 I-Node 확인)
- df -i (파일시스템의 I-Node 확인)

## File Type

- '-' : 일반 파일을 의미한다.
- 'd' : 디렉토리 파일을 의미한다.
- 'l' : 심볼릭 링크 파일을 의미한다.
- 'b' : Block Device 파일을 의미한다.
- 'c' : Character Device 파일을 의미한다.

- Symbolic Link

- Hard Link

- Device File
  - 각가의 디비아스 파일을 알면 하드웨어에 데이터를 기록하거나 읽을 수 있다.

- ls -alF

## touch (change file timestamps)

- touch [-crt] file-name
  - [-c : 인수로 지정한 파일이 존재하지 않아도 새로 작성하지 않는다.]
  - [-r : 최종 갱신일을 file 날짜에 맞춥니다.]
  - [-t : 최종 갱신일을 time으로 변경합니다.]
- touch test
- touch test{1..3}
- touch -a test (change only the access time)
- touch -t 202205100941 test
- ls -lc (time of last modification of file status information)

## cat (concatenate files and print on the standard output)

- cat > test.txt
- cat >> test.txt (append)
- ctrl + d (complete)

- cat a1 a2 a3
- cat a*

## tac (concatenate and print files in reverse)

- tac > test.txt
- tac >> test.txt (append)
- ctrl + d (complete)

## symbolic link

- ln -s original-file link-file (make links between files)
- ls -lF
- cat link-file

## hard link (원본 파일이 삭제되어도 사용할 수 있다.)

- 원본 파일과 I-Node 값이 같다.
- ln original-file link-file
- ls -lF
- cat link-file

## chattr (change file attributes on a Linux file system)

- chattr +i log (immutable: 파일을 수정할 수 없으며, 오직 관리자만 이 속성을 설정하거나 변경할 수 있다.)
- chattr -i log

## lsattr (list file attributes on a Linux second extended file system)

- lsattr log