# Navigation

## Print Working Directory

- pwd

## Change Directory

- cd /etc
- cd .. (Upper directory)
- cd ~ (Home directory)
- cd - (Previous directory)
- cd $TEMP (Change current directory to the directory defined by the environment variable "TEMP".)
- !!
- pushd /etc
- popd

## List

- ls
- ls -l
- ls -al
- ls -ld ( list directories themselves, not their contents)
- ls -alh (with -l and -s, print sizes like 1K 234M 2G etc.)
- ls -alS (sort by file size, largest first)
- ls -alX ( sort alphabetically by entry extension)
- ls -al *.html
- ls -l | grep "^d" (only directory)

## tree (list contents of directories in a tree-like format.)

- tree
- tree -p

## ln (make links between files)

- ln -s [original file path] [symbolic file path]
- rm link_test
