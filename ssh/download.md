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