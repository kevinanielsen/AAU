# Frontend
- recognizes the program and its meaning 
- signals errors and thus can fail (syntax errors, scoping errors, typing errors, etc.)
![[frontend.png]]
## Parsing
Identifies the programs that belong to the syntax of the language.
Its input is a sequence of characters and its output is abstract syntax.
Parsing is split into two steps:
- lexical analysis, which splits the input in “words” called tokens
- syntax analysis, which recognizes legal sequences of tokens
![[parsing.png]]
## Backend
- produces the target code
- uses many intermediate languages
- must not fail
![[backend.png]]