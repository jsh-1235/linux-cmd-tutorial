
# Utility

## History

- history
- history 5
- !444
- history -c (delete all)
- history -d 1
- history | awk '{a[$2]++}END{for(i in a){print a[i] " " i}}' | sort -rn | head -10

## help

- ls --help

## man (an interface to the system reference manuals)

- man ls
- man ls | grep 'sort'
- man ls | grep 'sort' | grep 'file'
- /search (navigation => n : forward, b: backward)

## date (print or set the system date and time)

- date

## cal (displays a calendar and the date of Easter)

- cal

## fortune (print a random, hopefully interesting, adage)

- fortune

## yes (print a random, hopefully interesting, adage)

- yes (output a string repeatedly until killed)
- yes I love you.
- ctrl + c (exit)
- jobs
- fg
- ps -aux | grep yes
- kill %1
- kill -9 %1

## rev (reverse lines characterwise)

- rev filename
- rev a.txt > b.txt

## sl (display animations aimed to correct users who accidentally enter sl instead of ls.)

- sl

## toilet (display large colourful characters)

- toilet Welcome
- toilet -f mono12 -F metal Welcome

## cmatrix (simulates the display from "The Matrix")

- cmatrix

## while (display animations aimed to correct users who accidentally enter sl instead of ls.)

- while true; do echo "$(date '+%D %T' | toilet -f term -F border --gay)"; sleep 1; done

## aafire

- apt install libaa-bin
- aafire

## asciiquarium (simulation of an aquarium using ASCII art)

- sudo add-apt-repository ppa:ytvwld/asciiquarium
- sudo apt-get update && sudo apt-get install asciiquarium
- asciiquarium
