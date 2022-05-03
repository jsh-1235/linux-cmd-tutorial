# Redirection

## Communication Channels

- stdin (0) : Keyboard
- stdout (1) : Terminal
- stderr (2) : Terminal

## stdout
- mailx -s "TEST MAIL" 

## Examples

- head -n 5 index.html > app.html (Redirects the output of the head command (detailed above) to a file "new_file")
- head -n 10 some_file >> exist_file
- ls -al /etc > result.txt
- ls -al /etc > result.txt 2> error.log
