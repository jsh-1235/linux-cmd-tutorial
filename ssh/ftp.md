# File Transfer Protocol

## ftp

- ftp ftp.example.com
- close
- quit

## lftp

- lftp ftp.example.com
- close
- quit

## sftp

- sudo sftp -i "aws-bt-key.pem" ubuntu@ec2-15-164-80-55.ap-northeast-2.compute.amazonaws.com
- sudo sftp -i "/home/jsh/aws-bt-key.pem" ubuntu@ec2-15-164-80-55.ap-northeast-2.compute.amazonaws.com
- pwd
- ls -al
- lls (Display remote directory listing)
- ? (사용 가능한 명령어)
- mget file
- mput file
- sh add.sh 8 8
- quit

## telnet

- 네트워크 서비스가 동작 중인지 확인
- telnet ec2-15-164-80-55.ap-northeast-2.compute.amazonaws.com http  (http 서버 상태 확인)
- GET /
