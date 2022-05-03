# ssh (secure shell)

- sudo apt purge openssh-server openssh-client
- sudo apt install openssh-server openssh-client

## Operation

- sudo service ssh start
- sudo service ssh stop
- ps -aux | grep ssh
- ssh jsh@192.168.0.72
- exit

## ssh-keygen

- ssh-keygen
- cd ~
- cd .ssh
- cat id_rsa.pub
- ssh-copy-id jsh@192.168.0.72
- ssh jsh@192.168.0.72 (No login required)

## AWS

- cd ../../mnt/c
- cd /mnt/c/Products/"Software Devlopment"/Web/DevOps/AWS/Setup/Keys
- cp aws-bt-key.pem ~/
- sudo ssh -i "aws-bt-key.pem" ubuntu@ec2-15-164-80-55.ap-northeast-2.compute.amazonaws.com
