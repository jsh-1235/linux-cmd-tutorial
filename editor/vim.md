# vim

## Insert mode

- shift + i
- a i o A I O

## Command mode

- ESC

## Execution mode

- :w new-file (새이름으로 저장하기)
- :wq (저장하고 나가기) (:x, ZZ)
- :q (나가기)
- :q! (변경 사항 취소 후 종료)
- :r new-file
- :e! (편집한 내용을 저장하지 않고, 최종 저장된 상태로 파일 다시 열기)
- . (마지막 실행했던 명령어를 다시 실행)

## find & replace

- /search-word
- ?search-word
- n (다음으로 일치하는 단어 검색)
- N (이전 일치하는 단어 검색)
- :%s/word1/word2
- :%s/word1/word2/gc

## move

- h j k l
- g G
- H M L
- w W e E b B
- ^, $
- :0 (해당 라인의 맨 앞으로 프롬프트를 이동)
- :10 (문서의 10번째 행으로 프롬프트를 이동)
- :$ (해당 라인의 맨 뒤로 프롬프트를 이동)

## 들여쓰기 & 내어쓰기

- >
- <

## Block

- v
- shift + v

## Select All

- gg v G

## copy

- yy (현재 줄 복사)
- y (copy)
- yw yb

## cut

- c

## paste

- p
- P

## replace

- r
- cw
- cc
- C
- R
- c$
- ~ (선택 문자 대소문자 변경)

## remove

- dd (현재 줄 잘라내기)
- x
- X
- dw
- db
- dW
- D
- dH dL

## undo & redo

- u
- ctrl + r

## 소/대문자 변경

- v (visual mode)
- ~

## setting

- :set hlsearch
- :set paste
- :set nopaste
- :set number
- :set nonumber
- :set ts=2

## configuration

- vi ~/.vimrc