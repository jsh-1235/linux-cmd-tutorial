# Environment

## Local Variable

- pi=3.14
- echo $pi
- set | grep pi
- unset pi

- session

- hi() { echo 'hi';}
- hi

## set

- set -o
- set -o | grep noclobber
- set -o noclobber (on : protection  overwrite)
- set +o noclobber (off)

- set -o | grep ignoreeof
- set -o ignoreeof (on : ctrl+d : protection logout)
- set +o ignoreeof (off)

## Global Variable

- env
- env | grep SHELL
- echo $SHELL
- echo $HISTSIZE
- echo $USER

- printenv

## Positional Parameter

- ls /etc /var /home
- set 1 2 3
- echo $1 $2 $3
- echo $*
- echo $#

## Path

- echo $PATH
- export PATH=/home/jsh/shells:$PATH
- export PATH=~/shells:$PATH
- echo $PATH | grep shells

- 환경 변수 영구 저장
- vim ~/.profile

```bash
if [ -d "$HOME/shells" ] ; then
    PATH="$HOME/shells:$PATH"
fi
```

- source .profile
