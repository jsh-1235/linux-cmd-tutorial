# File Read

## file (determine file type)

- text file or binary file
- file *
- file test.txt
- file ../../bin/ls
- cat -n ../../bin/ls

## cat (concatenate files and print on the standard output)

- cat backup
- cat -n index.html

## more (file perusal filter for crt viewing)

- more filename
- more +15 filename
- more +/string filename
- space : next page
- enter : next line
- q : exit

## less (opposite of more)

- less filename
- less -N filename
- 압축 해제 기능 및 메모리만 절약 기능

## head (file perusal filter for crt viewing)

- head filename
- head -n filename
- head -n 5 filename
- head -5 filename

## tail (file perusal filter for crt viewing)

- tail filename
- tail -n filename
- tail -n 5 filename
- tail -5 filename
- tail -f /var/log/filename
