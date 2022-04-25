# Find

- $PATH
- echo $PATH

## which

- which  returns  the pathnames of the files (or links) which would be executed in the current environment.
- which --help
- which ls

## whereis

- Locate the binary, source, and manual-page files for a command.
- whereis --help
- whereis ls

## History

- history
- history 5
- !444
- history -c (delete all)
- history -d 1
- history | awk '{a[$2]++}END{for(i in a){print a[i] " " i}}' | sort -rn | head -10

## locate (based in db)

- updatedb
- locate ls (apt install mlocate)
- locate ls -n 10
- locate index.html

## find (based in file)

- find - search for files in a directory hierarchy
- find . -name index.html
- find -name index.html
- find -name "*.html"
- ls /etc | grep a (prints all the files or directories in the "/etc" directory that have the letter 'a' in their name)
- grep -rl "find text" a.txt b.txt
- find . -type f
- find . -type f -name "c.log" -exec rm -f {} \;
