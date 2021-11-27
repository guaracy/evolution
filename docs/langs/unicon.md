# Icon e Unicon

Basicamente [Icon](https://www.cs.arizona.edu/icon) (1977) foi baseada em SNOBOL (1962) e [Unicon](https://unicon.sourceforge.io/)(1996) foi baseada em Icon com OO. Mas vamos ao que interessa.

# Sintaxe

```unicon linenums="1"
#
# Comentário
#
procedure main()
  a := 1
  b := 2*2
  write(a+b)
  write("Alô mundo")
end
```

Um pouco de C e um pouco de Pascal deixando o código muito mais limpo.  É perfeitamente possível eliminar o **begin** do Pascal ou **{** do C sem nenhum problema. A retirados do **;** (ponto e vírgula) também ajudam a deixar o código mais limpo. Esses elementos são apenas para o compilador e não são necessários para a resolução do problema.

Como aspecto negativo, vejo a adoção de **:=** do Pascal para a atribuição. Só para facilitar a compilação pois poderia ser inferido conforme o contexto. Algo como `#!unicon if a = 1` seria uma comparação e não uma atribuição.

Aquele **end** no final também seria desnecessário se adotasse uma endentação como [ABC](https://en.wikipedia.org/wiki/ABC_(programming_language)). Pelo menos não é necessário ponto ou ponto e vírgula como no Pascal. 

# Base numérica

Na realidade, unidades de medidas são mil vezes mais importantes do que bases numéricas no mundo real.  

Em algumas linguagens (não vou citar nomes) usamos **0b101** para base binária, **0x16A** para base hexadecimal, a base decimal inicial com um número mas, se for zero então é base octal. A coisa mais mal feita que eu já vi no universo. Se alguém escrever **05493** vai acusar erro e se escrever **0345** pode não ser o que o programador deseja.

Unicon utiliza a notação [base][r][número] sendo **base** um número decimal entre 2 e 36, seguido de **R** ou **r** e o número propriamente dito que deve respeitar a base [0..9 A..Z a..z]. A mas não se usa todas as bases. Use apenas as desejadas. 

# Unidades de media

Unicon possui alguns sufixos como K (kilo), M (mega), G (giga), T (tera) e P (peta). O problema é que são multiplos de 1024. 

```unicon linenums="1"
procedure main()
	write(1K)
	write(3K)
	write(5M)
end
```

e o resultado é:

```bash
1024
3072
5242880
```

Pessoalmente acho que as unidades deveriam ser uma propriedade das variáveis. Assim como temos inteiros, lógicos e outros, poderíamos ter centímetros, polegadas, kilo, grama, onças, etc., e variantes como km/h, kg/cm, etc.. Por exemplo:


```unicon
a = 23 cm 
a = a + 7 inch # a tem 40.78 cm
b = 4 oz       # 4 onças
c = a + b      # erro cm e oz são incompatíveis
```

Ah, mas vai dar muito trabalho para quem projetar o compilador. Besteira. Você prefere ter mais trabalho para desenvolver o sistema do que quem vai desenvolver o compilador. Pode ter certeza que o computador não vai se importar em alguns passos  a mais para entender o que você está querendo fazer. Sem contar que é muito mais fácil você errar do que o computador trabalhar. Ah, mas não tem problema. Besteira novamente. Pelo menos até a empresa perder 125 milhoes de dólares por [erros bestas](http://www.mundodametrologia.com.br/2014/07/confusao-de-unidades-causou-perda-da.html) que poderiam ser evitados com facilidade..

# Conversão de string para número

É possível uma operação do tipo `#!unicon a = 2 * "14"` o que retorna **28** mas a string deve ser um valor numérico válido. Não é tão inconsequente como php que aceitaria `#!unicon a = 2 * "14abc"`. Se retornasse `#!unicon "14abc14abc"` seria mais lógico.

# Resultado de expressões lógicas

Muitas vezes precisamos colocar um valor em determinada variável baseado em determinadas condições. É mais prático (e considero mais legível) utilizando o formato `#!unicon a := if cond then v1 else v2` do que usando `#!unicon if cond then a:=v1 else a:=v2`

```unicon linenums="1"
procedure main()
    a := if 1 > 2 then 5 else 6
    b := case a of {
        5 : "cinco"
        6 : "seis"
        default : "indefinido"
    }
    write(a)
    write(b)
end
```
Note que no **case** foram utilizadas chaves para abrir e fechar o bloco. Poderiam ter sido evitadas se tivessem escolhido um design diferente. Volto ao assunto na linguagem ABC.


# Finalmente

Depois retorno para escrever sobre algumas coisas na linguagem que também são interessantes como as repetições (every), generators. A parte de processamento de cadeias de caracteres é herdada do SNOBOL é muito boa e ainda possui ER. O funcionamento baseado em sucesso/falha. A [biblioteca](https://www2.cs.arizona.edu/icon/library/ipl.htm) também tem bastante coisa. 


No [Rosetta Code](http://rosettacode.org/wiki/Category:Icon) existem diversos exempĺos para avaliar. É claro que alguns programas são mais fáceis de entender que outros.

Também é possível baixar diversos [Livros](https://www2.cs.arizona.edu/icon/books.htm) sobre Icon.

[](http://rosettacode.org/wiki/Combinations_and_permutations#Icon_and_Unicon)