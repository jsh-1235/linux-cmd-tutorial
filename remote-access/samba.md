# SAMBA

- 삼바는 GPL 기반의 자유소프트웨어로 리눅스 윈도우 간 디렉토리, 파일, 프린터, USB 등을 공유하는데 사용할 수 있다.
- 삼바는 TCP/IP 기반의 NetBIOS상에서 동작하는 SMB(Server Manager Block) 프로토콜을 이용한다.
- 삼바는 설정한 그룹과 호스트명이 윈도우 Network Neighborhood에 컴퓨터 이름으로 표시된다.
- 또한 삼바를 사용하면 상대 호스트 IP 주소 대신 컴퓨터 이름을 이용하여 접속할 수 있다. (WINS: Windows Internet Name Service)
- GIFS (Common Internet File System)는 SMB를 인터넷까지 확장한 표준 프로토콜, 유닉스와 윈도우 환경을 동시에 지원한다.

## 삼바 서버의 구성 요소

- smbd (삼바 서버)
- nmbd (삼바 클라이언트)