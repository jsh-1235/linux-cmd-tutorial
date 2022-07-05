# dpkg (package manager for Debian)

- dpkg -L tree (설치한 패키지에 포함된 파일 확인)
- dpkg -l (설치된 패키지 확인)
- dpkg -l | grep tree
- dpkg -l | wc -l

- dpkg -r rename (Remove an installed package.)

## deb

- .deb은 데비안의 소프트웨어 패키지 포맷의 확장자이며 데비안 소프트웨어 포맷의 바이너리 패키지에서 가장 자주 사용되는 파일 이름이다.

- cat /etc/apt/sources.list
  - deb [URI] [distribution] [component] [component...]
  - deb <http://security.ubuntu.com/ubuntu/> focal-security main restricted
  - distribution : Ubuntu-20.04 LTS (focal)
