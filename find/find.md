# Find

## whatis (display one-line manual page descriptions)

- whatis ls

## which (which  returns  the pathnames of the files (or links) which would be executed in the current environment.)

- which ls
- which -a ls

## whereis (locate the binary, source, and manual page files for a command)

- whereis --help
- whereis ls

## locate (based in db)

- apt install mlocate
- updatedb
- locate ls
- locate ls -n 10
- locate index.html

## find (search for files in a directory hierarchy)

- find -name file1
- find -name "file*"
- find . -name file1

## find (type file or directory)

- find -type f
- find -type d
- find ./bin/ -type f
- find ./bin/ -type d
- find . -type f -name "c.log" -exec rm -f {} \;

## grep (print lines that match patterns)

- ls /etc | grep a
- ls -al | grep "f*"
- grep -rl "find text" a.txt b.txt

## comm (compare two sorted files line by line)

- comm a b

## cmp (compare two files byte by byte)

- cmp a b

## wc (print newline, word, and byte counts for each file)

- wc /etc/hosts


## cut (remove sections from each line of files)

- echo 'hello world' | cut -c 1-4
