# File Create

## tar (reverse lines characterwise)

- 파일 묶고 풀기 (파일 사이즈 증가)
  - tar -cvf modules.tar modules
  - tar -xvf modules.tar

- 여러 파일을 하나로 묶고 풀기
  - tar -cvf F.tar file1 file2 file3 ()
  - tar -rf F.tar file4 (추가)
  - tar -xvf F.tar (묶여지 파일을 풀기)

- 파일 압축 및 해제 (gzip)
  - tar -zcvf modules.tar.gz modules (압축 하기)
  - tar -zxvf modules.tar.gz (압축 풀기)

- 디렉토리 내용을 묶어서 압축하기 (bzip2)
  - tar -jcvf shells.tar.bz2 ../shells
  - tar -jxvf shells.tar.bz2 (압축 풀기)

## gzip (gzip, gunzip, zcat - compress or expand files)

- gzip rgb.txt
- gzip -k rgb.txt (keep (don't delete) input files)
- gzip -kv rgb.txt
- ls -lk rgb.txt.gz (File Size -> KB)

- gunzip rgb.txt.gz
- gunzip -f rgb.txt.gz (force overwrite of output file and compress links)
- gunzip -fvl rgb.txt.gz
- ls -l rgb.txt

- 압출 파일 내용 출력하기
  - zcat rgb.txt.gz

- 디렉토리 압축 및 해제
  - gzip -r modules/ (디렉토리 내의 모든 파일 압축)
  - gunzip -rvl modules/ (디렉토리 내의 모든 파일 압축 해제)

- 파일 용량 확인
  - du -a (파일까지 출력)
  - du -b (Byte, ls -l)
  - du -h (용량 단위 표시)
  - du -sh modules/

## bzip2 (bzip2, bunzip2 - a block-sorting file compressor, v1.0.8)

- bzip2 rgb.txt
- bzip2 -kv rgb.txt
- ls -l rgb.txt.bz2

- bunzip2 rgb.txt.bz2
- bunzip2 -fv rgb.txt.bz2
- ls -l rgb.txt

- 압출 파일 내용 출력하기
  - bzcat rgb.txt.bz2

## xz (xz, unxz, xzcat, lzma, unlzma, lzcat - Compress or decompress .xz and .lzma files)

- xz rgb.txt
- xz -kv rgb.txt
- ls -l rgb.txt.xz

- unxz rgb.txt.xz
- unxz -fv rgb.txt.xz
- unxz -fvl rgb.txt.xz
- ls -l rgb.txt

- 압출 파일 내용 출력하기
  - xzcat rgb.txt.xz
