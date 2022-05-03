# wsl (Windows Subsystem for Linux)

- 
- wsl --update
- wsl --list --online
- wsl -l -v
- wsl -t ubuntu-20.04 (terminate)

## Execution

- Ctr + R
- ws
- wsl -l -v
- ubuntu2004.exe
- sudo ssh -i "aws-bt-key.pem" ubuntu@ec2-52-78-209-69.ap-northeast-2.compute.amazonaws.com

## rsync

- sudo rsync -avz ~/projects/ -e "ssh -i aws-bt-key.pem" ubuntu@ec2-52-78-209-69.ap-northeast-2.compute.amazonaws.com:~/projects

- sudo rsync -ahrvz --delete --progress ~/projects/ -e "ssh -i aws-bt-key.pem" ubuntu@ec2-52-78-209-69.ap-northeast-2.compute.amazonaws.com:~/projects

## edit

- touch file{1..3}
- rm -f file{1..3}
