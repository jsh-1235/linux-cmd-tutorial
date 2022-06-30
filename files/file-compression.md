# File Create

## tar (reverse lines characterwise)

- 파일 묶고 풀기 (파일 사이즈 증가)
  - tar -cvf MODULES.tar MODULES
  - tar -xvf MODULES.tar

- 여러 파일을 하나로 묶고 풀기
  - tar -cvf MODULES.tar FILE1 FILE2 FILE3 ()
  - tar -rf MODULES.tar FILE4 (추가)
  - tar -xvf MODULES.tar (묶여지 파일을 풀기)

- 파일 압축 및 해제 (gzip)
  - tar -zcvf MODULES.tar.gz DIR (압축 하기)
  - tar -zxvf MODULES.tar.gz (압축 풀기)

- 디렉토리 내용을 묶어서 압축하기 (bzip2)
  - tar -jcvf MODULES.tar.bz2 ../DIR
  - tar -jxvf MODULES.tar.bz2 (압축 풀기)

## gzip (gzip, gunzip, zcat - compress or expand files)

- gzip FILE
- gzip -k FILE (keep (don't delete) input files)
- gzip -kv FILE
- ls -lh FILE.gz

- gunzip FILE.gz
- gunzip -f FILE.gz (force overwrite of output file and compress links)
- gunzip -fvl FILE.gz
- ls -lh FILE

- 압출 파일 내용 출력하기
  - zcat FILE.gz

- 디렉토리 압축 및 해제
  - gzip -r DIR/ (디렉토리 내의 모든 파일 압축)
  - gunzip -rvl DIR/ (디렉토리 내의 모든 파일 압축 해제)

- 파일 용량 확인
  - du -a (write counts for all files, not just directories)
  - du -b (Byte, ls -l)
  - du -h (print sizes in human readable format)
  - du -sh DIR/

## bzip2 (bzip2, bunzip2 - a block-sorting file compressor, v1.0.8)

- bzip2 FILE
- bzip2 -kv FILE
- ls -lh FILE.bz2

- bunzip2 FILE.bz2
- bunzip2 -fv FILE.bz2
- ls -lh FILE

- 압출 파일 내용 출력하기
  - bzcat FILE.bz2

## xz (xz, unxz, xzcat, lzma, unlzma, lzcat - Compress or decompress .xz and .lzma files)

- xz FILE
- xz -kv FILE
- ls -lh FILE.xz

- unxz FILE.xz
- unxz -fv FILE.xz
- unxz -fvl FILE.xz
- ls -lh FILE

- 압출 파일 내용 출력하기
  - xzcat FILE.xz
