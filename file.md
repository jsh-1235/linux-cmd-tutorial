# File

## Create

- touch file name
- cat > file name

## Update

- mv [−if] source_file target_file
- mv [−if] a.txt b.txt (rename)
- cp [−Pfip] source_file target_file

## Remove

- rm file name (...)
- rm -rf * (Deletes all files and directories belonging to the current directory)

## Read

- cat filename
- cat -n index.html
- more filename
- less filename
- head filename
- head -n filename
- tail filename
- tail -n filename
- nano filename

## Composition

- mkdir web; cd web; pwd;

## Pipes

- ls --help | more  (q: exit)
- ls -l /etc | more
- du /etc | sort -n | tail -n 5
- ls -al | sort -n
- ls -al | sort -nr

## Redirection

- head -n 5 index.html > app.html : Redirects the output of the head command (detailed above) to a file "new_file"
- head -n 10 some_file >> exist_file
- ls -al /etc > result.txt
- ls -al /etc > result.txt 2> error.log
- cat result.txt | more