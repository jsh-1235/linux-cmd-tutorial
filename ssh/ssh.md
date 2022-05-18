# ssh (secure shell)

- sudo apt purge openssh-server openssh-client
- sudo apt install openssh-server openssh-client

- vim /etc/ssh/sshd_config

## Operation

- sudo service ssh start
- sudo service ssh stop
- sudo vi /etc/ssh/sshd_config
- sudo service ssh restart

- ps -aux | grep ssh
- service --status-all | grep ssh

- nmap -PN localhost -p22 | grep ^22
- nc -zv localhost 22

- sudo tcpdump port 22

- ssh jsh@192.168.0.9 (DESKTOP-JSH)
- ssh jsh@192.168.0.72 (DESKTOP-SLAVE)
- exit

## ssh-keygen

- ssh-keygen
- cd ~
- cd .ssh
- cat id_rsa.pub
- ssh-copy-id jsh@192.168.0.72
- ssh jsh@192.168.0.72 (No login required) (ssh client)
- ssh -l jsh 192.168.0.72
- sudo service ssh start (ssh server)

## AWS

- cd ../../mnt/c
- cd /mnt/c/Products/"Software Devlopment"/Web/DevOps/AWS/Setup/Keys
- cp aws-bt-key.pem ~/
- sudo ssh -i "aws-bt-key.pem" ubuntu@ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com
- sudo ssh -i "aws-bt-key.pem" ubuntu@ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com ls -al
- exit

## scp (OpenSSH secure file copy)

- sudo scp -i "aws-bt-key.pem" ubuntu@ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com:~/scp-file .
- cat scp-file

## rsync (a fast, versatile, remote (and local) file-copying tool)

- sudo rsync -avz ~/projects/ -e "ssh -i aws-bt-key.pem" ubuntu@ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com:~/projects

- sudo rsync -ahrvz --delete --progress ~/projects/ -e "ssh -i aws-bt-key.pem" ubuntu@ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com:~/projects
