# Evolução das linguagens de programação

??? warning
    ## Texto em desenvolvimento

## Geral

Mais de 60 anos desde a criação da primeira linguagen de programação de **alto nível** e, para mim, a única coisa que evoluiu para o programador foi o editor.

As linguagens/framaworks utilizados para desenvolvimento se tornaram extremamente complexos fazendos com que o programador tenha que perder tempo se preocupando com detalhes superfluos que nada tem a ver com a resolução do problema que é o motivo principal da sua atividade.

O objetivo deste documento é olhar algumas linguagens e, do meu ponto de vista, mostrar algumas coisas que eu achei que deveriam estar nas novas linguagens e outras coisas que foram implementadas e eu não gostei. Não interessam alguns aspectos técnicos como, se a linguagem possui um **sort** ele foi implementado como Bubble, Quick ou outro. 

Parece que a maioria dos programadores simplesmente não se preocupam com as dificuldades e, qualquer discussão sobre as linguagens é muito mais emocional do que racional. Como o programador utiliza a lógica para o desenvolvimento, deveria utilizá-la para outras tarefas também. Qualquer programador que se diga plenamente satisfeito com a linguagem utilizada ou:

- não conhece outras linguagens (ou a própria) e/ou
- não está sendo lógico na discussão

## Compiladores e interpretadores

Grande parte simplesmente pega alguma coisa, faz alguma alteração e diz: **Agora uma nova e revolucionária linguagem.** Na realidade, apenas a mesma coisa de antes com algumas alterações que facilita, dificultam ou deixam no mesmo o desenvolvimento do programa por parte do programador.

Alguns não possuem conhecimento do mundo real ou apenas ignoram para facilitar o trabalho deles quando, na realidade, deveria ser o contrário. Vejamos o caso de uma matriz

Tem gente que, se você pergunta: *Me mostre o mundo!"*. Ela olha para baixo, enfia o dedo no umbigo e diz: *Tá aqui, ó!*. Uma matriz só inicia em zero pois quem fez a linguagem decidiu assim. Atualmente, estou desenvolvendo um sistema em que um dos itens deve ser calculado para ângulos entre 7º e 49º para que sejam escolhidos os melhores rendimentos. Se começa em zero, tenho que definir uma matriz de (49-7) posições. Claramente temos a primeira dificuldade. O nosso programa já inicia diferente do nosso problema. Para armazenar os cálculos efetuados para o ângulo 8, tenho que armazenar na posição (8-7), isto é, mais uma operação desnecessária . E assim vai a complexidade da programação. Usando Lazarus/Delphi, uma matriz pode iniciar em um número arbitrário (o que engloba sua array iniciando em zero). No meu caso, utilizei uma matriz "[angulo_inicial..angulo_final] of record" e no program tenho estruturas como "for a in [angulo_inicial..angulo_final]". Não consigo ver nada mais lógico, inteligente e racional que a proposta do Pascal. Posso ter array com um intervalo como [-10..10], [1950..2030], etc.. Para ficar melhor, só se tivesse algo como um step tipo [1950..2030,10] que iniciaria no ano de 1950 de 10 em dez anos até 2030. Os meses do ano são de 1 a 12. Seria mais lógico definir um array como [0..12] (13 posições) e utilizar de 1..12 do que insistir no mês zero. 
