# expressions

## seq (print a sequence of numbers)

- seq 10
- seq 100

- seq -s ' ' 50 (use STRING to separate numbers)
- seq -s '-' 10 50

- seq -w -s ' ' 100 (equalize width by padding with leading zeroes)

- seq -f "%.5f" 10 0.5 100
- seq -s '/' -f "%.5f" 10 0.5 100

- seq -f "%.3e" 0 0.5 20
- seq -s ' ' -f "%.3e" 0 0.5 20

- seq -f "%g" 0 0.5 50

- seq 100 100 500
- seq 100 100 500 | nl > test

## factor (factor numbers)

- factor 12 (12: 2 2 3)
- factor
- ctrl + d (exit)

## expr (evaluate expressions)

- which expr (/usr/bin/expr)
- type expr (expr is hashed (/usr/bin/expr))

- expr 5 + 3
- expr 5 - 3
- expr 5 '*' 3
- expr 5 \* 3
- expr 5 '/' 3
- expr 5 '%' 3

- expr 1 = 1
- expr 1 '!=' 1
- expr 2 '>' 1
- expr 2 \> 1
- echo $?

- expr 1 \| 2 (1)
- expr 0 \| 2 (2)
- expr '' \| 2 (2)

- expr 1 \& 2 (1)
- expr 0 \& 2 (0)
- expr '' \& 2 (0)

- expr match programming pro
- expr substr programming 1 5
- expr index programming p
- expr length programming

## let (Evaluate arithmetic expressions.)

- type let (let is a shell builtin)
- help let

- a=10 && echo $a
- let b=$a && echo $b
- let a++ && echo $a
- let b++ && echo $b

- let a=2**4 && echo $a
- let a=(2 ** 4) && echo $a

- let a=(1==1) && echo $a
- let a=(1/!=1) && echo $a

- let a=(1 \& 1) && echo $a
- let a=(1 \& 0) && echo $a
- let a=(0 \& 1) && echo $a
- let a=(0 \& 0) && echo $a

- let a=(1 \| 1) && echo $a
- let a=(1 \| 0) && echo $a
- let a=(0 \| 1) && echo $a
- let a=(0 \| 0) && echo $a

- let a=2\>1?1000:500; echo $a

- a=$((2+4)); echo $a
- a=$((2+4)) && echo $a

- a=$((2 > 4)) && echo $a
- a=$((2 < 4)) && echo $a

- a=$((2 << 2)) && echo $a
- a=$((8 >> 2)) && echo $a
