# Wildcard

- ? : Matches any single character (Question)
- * (Asterisk) : Matches anything (any number of characters)
- ^ (Caret)
- ! (Exclamation)
- [..] : character classes
  - ls file[12]
  - ls file[1-3]
- {} (Brace)
  - 문자열 생성 허용
  - 와일드 카드와 유사하지만 대상 파일 또는 디렉토리가 존재할 필요가 없다.
  - mkdir dir{1,2,3}
  - mkdir dir{1..10}
  - mkdir -p bin/{dev,qa,prod}

- g?f (gAF, gif, gof)
- ?? (임의의 두 글자)
- [gif] (g, i, f 중 한 글자)
- [a-z] (a에서 z까지 알파벳 소문자 한 글자)
- [^gif] (g, i, f  이외의 한 글자)
- [^a-z] (a에서 z까지 알파벳 소문자 이외 모든 문자)

- [*.^] (asterisk)
