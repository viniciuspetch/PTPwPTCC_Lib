# PTPwPTCC_Lib
Set of instances used for the Profitable Tour Problem with Passengers and Time and Cost Constraints.

Conjunto de instâncias utilizadas pelo Problema do Passeio Lucrativo com Passageiros e Restrições de Tempo e Custo.

## [PT-BR] Criação da instância

Foram geradas 156 instâncias, divididas em 3 grupos (g, h, i) de 4 tipos cada (a, b, c, d), totalizando 12 configurações, onde cada configuração contém uma instância de cada tamanho: 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 150, 200, e 300. Também foram geradas mais 24 instâncias de 100 vértices, sendo 2 instâncias por configuração, nomeados com o sufixo -t1 e -t2. Estas instâncias serão utilizadas pelo irace, como instâncias de treinamento (t1) e teste (t2). Dentro de cada grupo, foram geradas instâncias simétricas (tipos a e c) e assimétricas (tipos b e d). A simetria de uma instância determina se os grafos de custo e tempo e os pedágios das arestas serão simétricos ou não.

Os parâmetros foram divididos em 2 categorias: os parâmetros comuns a todas as configurações tiveram os seus valores escolhidos de forma arbitrária, enquanto os parâmetros que variam entre as configurações foram sorteados, de acordo com limites inferiores e superiores estipulados a eles.

Para a geração dos pedágios, para cada aresta foi dado uma probabilidade de conter um pedágio. Caso a aresta contenha um, o courier será obrigado a pagar o valor do pedágio caso a quantidade de passageiros no veículo seja inferior à quantidade estipulada por cada pedágio.

O universo de tempo é responsável por limitar os valores da janela de tempo, controlando-as de tal forma que não existam janelas de tempo que não podem ser alcançandas ou buscando limitar o tamanho da solução criando janelas que só serão disponíveis no começo da solução. O valor do universo de tempo é calculado a partir da média das arestas do grafo de tempo, multiplcado pelo tamanho do grafo e por fim, multiplicado por uma porcentagem.

Para o cálculo da janela de tempo, o universo de tempo será dividido em 3 setores, com o primeiro setor sendo de 0% a 30% do universo de tempo, o segundo setor sendo de 35% a 65% do universo de tempo e o terceiro setor sendo de 70% a 100% da janela de tempo. O limite inferior de cada janela de tempo será sorteada de tal forma que o seu valor esteja dentro de um desses três setores. O limite superior da janela de tempo é então calculado a partir do valor do caminho mais curto no grafo de tempo entre o vértice de origem e o vértice de destino do passageiro, multiplicado por uma porcentagem.

A Tabela 1 mostra os parâmetros selecionados para todas as configurações, com a capacidade máxima do veículo, o valor mínimo e máximo para as arestas no grafo de tempo, os bônus dos vértices, os tempos dos vértices, o custo do pedágio, a porcentagem utilizada para o cálculo do limite superior da janela de tempo, a porcentagem utilizada para o cálculo da tarifa do passageiro, o quantidade de passageiros utilizado como ponto de corte para o pedágio, a quantidade de passageiros por vértice, e a porcentagem utilizada no cálculo do universo de tempo.

Tabela 2 mostra os parâmetros sorteados para as configurações do grupo g, a Tabela 3 mostra os parâmetros sorteados para as configurações do grupo h, e Tabela 4 mostra os parâmetros sorteados para as configurações do grupo i. As tabelas definem o valor mínimo e máximo das arestas do grafo de custo, se os grafos de custo e tempo serão simétricos ou assimétricos, e a probabilidade de uma aresta conter um pedágio.

| Variável | Mínimo | Máximo | 
| --- | :---: | :---: |
| Tempo da aresta | 600 | 1200 | 
| Bônus do vértice | 200 | 700 | 
| Tempo do vértice | 700 | 1100 | 
| Custo do pedágio | 3000 | 4000 | 
| Janela de tempo | 200% | 300% | 
| Tarifa máxima | 200% | 400% | 
| Capacidade do veículo | 4 passageiros + motorista |-| 
| Limite do pedágio | 2 | 3 | 
| Quantidade de passageiros por vértice | 2*capacidade | 3*capacidade | 
| Tamanho do universo de tempo | 40% | 70% |

*Tabela 1. Parâmetros utilizados na geração das instâncias, comum a todos os grupos*

| Variável | ga | gb | gc | gd | 
| --- | :---: | :---: | :---: | :---: | 
| Custo mínimo da aresta | 676 | 888 | 715 | 908 | 
| Custo máximo da aresta | 966 | 1188 | 983 | 1252 | 
| Simétrico? | Sim | Não | Sim | Não | 
| Chance de adicionar pedágio a uma aresta | 27% | 22% | 34% | 37% | 
 
*Tabela 2. Parâmetros utilizados na geração das instâncias do grupo g*

| Variável | ha | hb | hc | hd
| --- | :---: | :---: | :---: | :---: | 
| Custo mínimo da aresta | 560 | 777 | 630 | 781
| Custo máximo da aresta | 926 | 1051 | 944 | 1111
| Simétrico? | Sim | Não | Sim | Não | 
| Chance de adicionar pedágio a uma aresta | 30% | 27% | 35% | 32% 
 
*Tabela 3. Parâmetros utilizados na geração das instâncias do grupo h*

| Variável | ia | ib | ic | id
| --- | :---: | :---: | :---: | :---: | 
| Custo mínimo da aresta | 826 | 661 | 649 | 890
| Custo máximo da aresta | 1110 | 1017 | 931 | 1182
| Simétrico? | Sim | Não | Sim | Não | 
| Chance de adicionar pedágio a uma aresta | 23% | 29% | 38% | 32% 
 
*Tabela 4. Parâmetros utilizados na geração das instâncias do grupo i*

Para as instâncias do grupo h e i, o custo dos pedágios são recalculados de acordo com o custo da aresta que o contém. A Tabela 5 mostra como os custos são modificados. Para as instâncias do grupo i, os custos das arestas são recalculados de acordo com o bônus dos vértices nos quais a aresta é incidente. Neste caso, a incidência de uma aresta sobre um vértice significa que uma aresta (i,j) é incidente sobre os vértices i e j. A Tabela 6 mostra como os custo são modificados. Para as instâncias do grupo i, a quantidade de passageiros em um vértice é definida a partir da quantidade do bônus do vértice e da capacidade do veículo. A Tabela 7 mostra quais são os valores estipulados.

| Custo da aresta | >= 900	 | < 900, >= 500	 | < 500  |
| Modificação no custo do pedágio | 0 | 1000 | Entre 2500 e 3000 |

*Tabela 5. Ajuste do custo do pedágio de acordo com o custo da respectiva aresta, para as instâncias do grupo h e i*

Se o bônus do vértice for:

`>= 550	< 550, >= 350	< 350`

É somado ao custo de todas as arestas que contém aquele vértice:

`Entre 300 e 500	Entre 100 e 200	Entre -100 e -150`

*Ajuste do custo da aresta de acordo com o bônus dos vértices relacionados, para as instâncias do grupo i*

Se o bônus do vértice for:

`>= 300	< 300, >= 200	< 200`

A quantidade de passageiros no vértice será:

`Entre 3C e 4C 	Entre 2C e 3C	Entre 1C e 2C`

*Quantidade de passageiros por vértice de acordo com o bônus do vértice, para as instâncias do grupo i, a partir da capacidade do veículo C*
