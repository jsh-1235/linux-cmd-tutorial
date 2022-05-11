# File Create

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

- ln original-file link-file
- ls -lF
- cat link-file
