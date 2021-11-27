ABC

A linguagem [ABC](https://homepages.cwi.nl/~steven/abc/)(1987) baseada em ALGO e, tendo como sua filha mais famosa Python.

A grande sacada da linguagem foi a endentação dos blocos, eliminando chaves e outras frescuras como begin end. COBOL até tinha alguns detalhes de endentação para o código mas não tão bons como ABC. Tirando algumas linguagens onde a endentação não faria muito sentido, todo o programador endenta a sua linguagem. O mais lógico seria usar esta endentação para uma finalidade mais nobre.

Como não existe um salientador de sintaxe para ABC no pygments (utilizado aqui), vou utilizar outra linguagem para ver como funciona. Apesar de ser interessante, o ambiente de desenvolvimento da linguagem não usa processador de texto para os programas. É mais como um REPL e imagens. Mas não vamos falar sobre isto agora. Um exemplo que conta na página:

```cobol linenums="1" hl_lines="6"
HOW TO GUESS:
    PUT choice {0..99} IN number
    WRITE "Guess my number from 0 to 99: "
    READ guess EG 0
    WHILE guess <> number:
        SELECT:
            guess < number: WRITE "Try higher: "
            guess > number: WRITE "Try lower: "
        READ guess EG 0
    WRITE "Yes! Well done" /
```

Basicamente, quando iniciamos um novo bloco é utilizado o dois pontos **:**. O bloco é então endentado e, quando terminamos a endentação, o bloco é encerrado sem a necessidade de caracteres especiais.

Um detalhe interessante é o select da linha 6. A opções também aceitam comparações como `guess < number`. 