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

## touch (change file timestamps)

- touch [-crt] file-name
  - [-c : 인수로 지정한 파일이 존재하지 않아도 새로 작성하지 않는다.]
  - [-r : 최종 갱신일을 file 날짜에 맞춥니다.]
  - [-t : 최종 갱신일을 time으로 변경합니다.]
- touch file-name
- touch -a file-name (change only the access time)
- touch file-name{1..3}
- touch -t 202205100941

## cat

- cat > test.txt
- cat >> test.txt (append)
- ctrl + d (complete)

## tar (reverse lines characterwise : 파일 묶고 풀기)

- tar -cvf a.tar a
- tar -xvf a.tar
- tar -zcvf a.tar.gz a (압축 하기)
- tar -zxvf a.tar.gz (압축 풀기)
- tar -cvf F.tar file1 file2 file3 (여러 파일을 하나로 묶기)
- tar -rf F.tar file4
- tar -xvf F.tar (묶여지 파일을 풀기)

## gzip (gzip, gunzip, zcat - compress or expand files)

- gzip rgb.txt
- ls -l rgb.txt.gz
- gunzip rgb.txt.gz
- zcat rgb.txt.gz (압출 파일 내용 출력하기)
- ls -l rgb.txt

## bzip2 (bzip2, bunzip2 - a block-sorting file compressor, v1.0.8)

- bzip2 rgb.txt
- ls -l rgb.txt.bz2
- bunzip2 rgb.txt.bz2
- bzcat rgb.txt.bz2 (압출 파일 내용 출력하기)
- ls -l rgb.txt

## xz (xz, unxz, xzcat, lzma, unlzma, lzcat - Compress or decompress .xz and .lzma files)

- xz rgb.txt
- ls -l rgb.txt.xz
- unxz rgb.txt.xz
- xzcat rgb.txt.xz (압출 파일 내용 출력하기)
- ls -l rgb.txt

## Symbolic link

- ln -s original-file link-file (make links between files)
- ls -lF
- cat link-file

## Hard link (원본 파일이 삭제되어도 사용할 수 있다.)

- 원본 파일과 I-Node 값이 같다.
- ln original-file link-file
- ls -lF
- cat link-file

