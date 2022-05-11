# Download

## wget (The non-interactive network downloader.)

- wget -O img.jpg https://unsplash.com/photos/ZMg3FA871Oo/download?ixid=MnwxMjA3fDB8MXxhbGx8Mnx8fHx8fDJ8fDE2NTAzNDA4NTI&force=true
- wget -r http://www.example.com/index.html (찾아낸 링크를 계속 따가가며 모든 파일을 다운로드한다.)
- wget -i URL.txt

## curl (transfer a URL)

- curl -O http://www.example.com/index.html
- curl -O http://www.example.com/file[01-10].txt

## xdg-open (opens a file or URL in the user's preferred application)

- xdg-open img.jpg

## eog (image viewer and cataloguer)

- eog img.jpg
- eog img.jpg &
- ctl + c (exit)

## feh (image viewer and cataloguer)

- feh img.jpg

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
