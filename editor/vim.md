# vim

## Insert mode

- shift + i
- a i o A I O

## Command mode

- ESC

## Execution mode

- :e! (모든 작업 취소)
- :w new-file (새이름으로 저장하기)
- :wq (저장하고 나가기) (:x, ZZ)
- :q (나가기)
- :q! (변경 사항 취소 후 종료)
- :r new-file

## find & replace

- /search-word
- ?search-word
- :%s/word1/word2
- :%s/word1/word2/gc

## move

- h j k l
- g G
- H M L
- w W e E b B
- ^, $

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

## setting

- :set hlsearch
- :set paste
- :set nopaste
- :set number
- :set nonumber
- :set ts=2

## configuration

- vi ~/.vimrc

