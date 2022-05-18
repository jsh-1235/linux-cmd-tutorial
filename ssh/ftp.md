# File Transfer Protocol

- 익명(Anonymous) ftp
- 계정 ftp

## ftp

- ftp ftp.kaist.ac.kr
- ls (remote)
- !ls (local)
- close
- quit

## lftp

- lftp ftp.example.com
- close
- quit

## sftp

- sudo sftp -i "aws-bt-key.pem" ubuntu@ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com
- sudo sftp -i "/home/jsh/aws-bt-key.pem" ubuntu@ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com
- pwd
- ls -al
- !ls or lls (Display remote directory listing)
- ? or help (사용 가능한 명령어)

- get math ./download
- put ./download/math ./download
- mget file
- mput file

- sh add.sh 8 8
- quit

## telnet

- 네트워크 서비스가 동작 중인지 확인
- telnet ubuntu@ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com http  (http 서버 상태 확인)
- GET /
