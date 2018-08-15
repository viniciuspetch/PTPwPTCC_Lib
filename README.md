# PTPwPTCC_Lib
Set of instances used for the Profitable Tour Problem with Passengers and Time and Cost Constraints

## [PT-BR] Criação da instância

Foram geradas 156 instâncias, divididas em 3 grupos (g, h, i) de 4 tipos cada (a, b, c, d), totalizando 12 configurações, onde cada configuração contém uma instância de cada tamanho: 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 150, 200, e 300. Também foram geradas mais 24 instâncias de 100 vértices, sendo 2 instâncias por configuração, nomeados com o sufixo -t1 e -t2. Estas instâncias serão utilizadas pelo irace, como instâncias de treinamento (t1) e teste (t2). Dentro de cada grupo, foram geradas instâncias simétricas (tipos a e c) e assimétricas (tipos b e d). A simetria de uma instância determina se os grafos de custo e tempo e os pedágios das arestas serão simétricos ou não.

Os parâmetros foram divididos em 2 categorias: os parâmetros comuns a todas as configurações tiveram os seus valores escolhidos de forma arbitrária, enquanto os parâmetros que variam entre as configurações foram sorteados, de acordo com limites inferiores e superiores estipulados a eles.

Para a geração dos pedágios, para cada aresta foi dado uma probabilidade de conter um pedágio. Caso a aresta contenha um, o courier será obrigado a pagar o valor do pedágio caso a quantidade de passageiros no veículo seja inferior à quantidade estipulada por cada pedágio.

A Tabela 1 mostra os parâmetros selecionados para todas as configurações, enquanto a Tabela 2 mostra os parâmetros sorteados para as configurações do grupo g, a Tabela 3 mostra os parâmetros sorteados para as configurações do grupo h, e Tabela 4 mostra os parâmetros sorteados para as configurações do grupo i.
***
|Variável | Mínimo | Máximo | 
|---|:---:|:---:|
|Tempo da aresta | 600 | 1200 | 
|Bônus do vértice | 200 | 700 | 
|Tempo do vértice | 700 | 1100 | 
|Custo do pedágio | 3000 | 4000 | 
|Janela de tempo | 200% | 300% | 
|Tarifa máxima | 200% | 400% | 
|Capacidade do veículo | 4 passageiros + motorista |-| 
|Limite do pedágio | 2 | 3 | 
|Quantidade de passageiros por vértice | 2*capacidade | 3*capacidade | 
|Tamanho do universo de tempo | 40% | 70% |

*Parâmetros utilizados na geração das instâncias, comum a todos os grupos*
***
***
 | Variável | ga | gb | gc | gd | 
 | --- | :---: | :---: | :---: | :---: | 
 | Custo mínimo da aresta | 676 | 888 | 715 | 908 | 
 | Custo máximo da aresta | 966 | 1188 | 983 | 1252 | 
 | Simétrico? | Sim | Não | Sim | Não | 
 | Chance de adicionar pedágio a uma aresta | 27% | 22% | 34% | 37% |
 
*Parâmetros utilizados na geração das instâncias do grupo g*
***
 | Variável | ha | hb | hc | hd
 | --- | :---: | :---: | :---: | :---: | 
 | Custo mínimo da aresta | 560 | 777 | 630 | 781
 | Custo máximo da aresta | 926 | 1051 | 944 | 1111
 | Simétrico? | Sim | Não | Sim | Não | 
 | Chance de adicionar pedágio a uma aresta | 30% | 27% | 35% | 32%
 
*Parâmetros utilizados na geração das instâncias do grupo h*
***
 | Variável | ia | ib | ic | id
 | --- | :---: | :---: | :---: | :---: | 
 | Custo mínimo da aresta | 826 | 661 | 649 | 890
 | Custo máximo da aresta | 1110 | 1017 | 931 | 1182
 | Simétrico? | Sim | Não | Sim | Não | 
 | Chance de adicionar pedágio a uma aresta | 23% | 29% | 38% | 32%
 
*Parâmetros utilizados na geração das instâncias do grupo i*
***

Para as instâncias do grupo h e i, o custo dos pedágios são recalculados de acordo com o custo da aresta que o contém. A Tabela 5 mostra como os custos são modificados. Para as instâncias do grupo i, os custos das arestas são recalculados de acordo com o bônus dos vértices nos quais a aresta é incidente. Neste caso, a incidência de uma aresta sobre um vértice significa que uma aresta (i,j) é incidente sobre os vértices i e j. A Tabela 6 mostra como os custo são modificados. Para as instâncias do grupo i, a quantidade de passageiros em um vértice é definida a partir da quantidade do bônus do vértice e da capacidade do veículo. A Tabela 7 mostra quais são os valores estipulados.
***
Se o custo da aresta for:

`>= 900	< 900, >= 500	< 500`

É somado ao custo do pedágio da aresta, se existir:

`0	1000	Entre 2500 e 3000`

*Ajuste do custo do pedágio de acordo com o custo da respectiva aresta, para as instâncias do grupo h e i*
***
Se o bônus do vértice for:

`>= 550	< 550, >= 350	< 350`

É somado ao custo de todas as arestas que contém aquele vértice:

`Entre 300 e 500	Entre 100 e 200	Entre -100 e -150`

*Ajuste do custo da aresta de acordo com o bônus dos vértices relacionados, para as instâncias do grupo i*
***
Se o bônus do vértice for:

`>= 300	< 300, >= 200	< 200`

A quantidade de passageiros no vértice será:

`Entre 3C e 4C 	Entre 2C e 3C	Entre 1C e 2C`

*Quantidade de passageiros por vértice de acordo com o bônus do vértice, para as instâncias do grupo i, a partir da capacidade do veículo C*
***
