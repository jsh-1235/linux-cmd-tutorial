# telnet 개요

- 상이한 운영체제 호스트 간의 원격 로그인 서비스
- 사용자가 다른 곳에 위치한 시스템에 온라인으로 연결하여 사용하게 해주는 서비스이다.
- 시스템에 접속하여 로컬에서와 같은 작업을 가능하게 해준다.

## telnet

- telnet ubuntu@ec2-15-164-95-222.ap-northeast-2.compute.amazonaws.com http  (http 서버 상태 확인)
- telnet 192.168.0.72 http
- GET /

## telnet-server

- yum -y install telnet-server
- yum info telnet-server
- cat /etc/pam.d/remote
- service xinetd start