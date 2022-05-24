# File Transfer Protocol

- FTP는 TCP/IP를 이용하여 FTP 서버와 FTP 클라이언트간 파일을 전송(Transport)하기 위한 프로토콜이다.
- FTP는 기본적으로 등록된 사용자 (계정 ftp)만 접속할 수 있으나 익명의 사용자 (Anonymous User)를 지원하는 경우도 있다.
- 단, 익명 사용자는 보안에 취약할 수 있으므로 권장하지 않는다.
- FTP는 명령 전달을 위한 제어 포트(21)와 데이터 전달을 위한 전송 포트(20)를 각각 사용하며, 동작 방식으로 능등 모드(Active mode)와 수동 모드(Passive mode)가 있다.
- 제어 포트 (21) : 사용자 인증, 명령 전달
- 전송 포트 (20) : 데이터 전달

## ftp port

- cat /etc/services | grep ftp

## ftp status

- ps -aux | grep ftp
- service --status-all | grep ftp

- nmap -PN localhost -p21 | grep ^21
- nc -zv localhost 21

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

## vsftpd (Very Secure FTP Daemon)

## telnet

- 네트워크 서비스가 동작 중인지 확인
- telnet ubuntu@ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com http  (http 서버 상태 확인)
- GET /
