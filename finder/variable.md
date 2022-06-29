# variable

## Local Variable (지역 변수)

- set
  - Change the value of shell attributes and positional parameters
  - display the names and values of shell variables.

- PI=3.14
- echo $PI
- set | grep PI
- unset PI

## Global Variable (전역 변수)

- env
  - run a program in a modified environment
  -
- export PI=3.14
- env | grep PI
- bash
  - echo $PI

## Positional parameters

- set 1 2 3 4
  - echo $0
  - echo $1
  - echo $2
  - echo $3

- set $(date)
  - echo $0 (bash)
  - echo $1 (Fri)
  - echo $2 (Jun)
  - echo $3 (17)
  - echo $4 (18:37:58)
  - echo $5 (KST)
  - echo $5 (2022)

## path

- env (run a program in a modified environment)

- echo $PATH
- export PATH=/home/jsh/shells:$PATH
- export PATH=~/shells:$PATH
- echo $PATH | grep shells

- 환경 변수 영구 저장
  - vim ~/.profile
  - PATH=~/shells:$PATH

- vim hi.sh
  - echo 'hi'
- chmod +x hi.sh
- ./hi.sh

- export PATH=~/bin:$PATH
- echo $PATH | grep ~/bin
- . .profile
- hi.sh
