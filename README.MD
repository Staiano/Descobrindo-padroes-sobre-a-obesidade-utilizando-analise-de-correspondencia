# Ciência de Dados e Obesidade: Descobrindo Padrões com Análise de Correspondência

10 de julho de 2024

## Análise de Correspondência

Olá! Mais um artigo dos meus estudos de ciência de dados!

Nas últimas 2 semanas no MBA da  [MBA USP/Esalq](https://www.linkedin.com/school/mbauspesalq/)  de Data Science e Analytics que estou cursando, tive a matéria de Análise de Correspondência Simples e Múltipla. Se você está acompanhando meus artigos no LinkedIn, sabe que estou escrevendo sobre vários temas diferentes para passar por diversos tópicos de ciência de dados e aprender um pouco mais sobre cada um deles.

  

### Artigos anteriores

-   [Projeto de Ciência de Dados: Identificando Jogadores Semelhantes a Mbappé através de Clusters](https://www.linkedin.com/pulse/projeto-de-ci%25C3%25AAncia-dados-identificando-jogadores-estaiano-j%25C3%25BAnior-tgsaf/?trackingId=00vvJtcATxrm2aEQqhD2ng%3D%3D)
-   [Ciencia de dados no RPG de mesa! Analise fatorial dos atributos dos nossos monstros favoritos](https://www.linkedin.com/pulse/ciencia-de-dados-rpg-mesa-analise-fatorial-dos-nossos-pedro-tqcuf/?trackingId=U32mJmAcxqUGnBqP6lei%2Fw%3D%3D)
-   [Pix vs. TED: Previsões da Ciência de Dados para o Futuro das Transações Financeiras no Brasil](https://www.linkedin.com/pulse/pix-vs-ted-previs%25C3%25B5es-da-ci%25C3%25AAncia-de-dados-para-o-das-estaiano-j%25C3%25BAnior-qydof/?trackingId=YUcF91RRVum3HJ%2BpjZHuGg%3D%3D)

  

No MBA, tivemos aulas de Análise de Correspondência Simples e Múltipla, e eu não poderia deixar de fazer um estudo e um artigo sobre isso para praticar o que foi ensinado pelo excelente professor  [Wilson Tarantin Junior](https://www.linkedin.com/in/wilson-tarantin-junior-359476190/)  .

  

### Base de dados

A Análise de Correspondência é uma técnica que analisa o quanto variáveis qualitativas estão associadas entre si. Para fazer um estudo adequado, precisei de um banco de dados que tivesse em sua maioria dados qualitativos.

Em minha busca, encontrei no  [Kaggle](https://www.kaggle.com/datasets/fatemehmehrparvar/obesity-levels/data)  um ótimo estudo sobre obesidade. O banco de dados possui informações sobre os graus de obesidade, incluindo hábitos alimentares e atividades físicas, entre outras estatísticas de moradores da Colômbia, Peru e México.

Este banco de dados tem 17 colunas, ou seja, temos 17 variáveis de informações para trabalhar. Destas, 9 são variáveis qualitativas e 8 quantitativas. Estas 8 variáveis quantitativas foram transformadas em qualitativas para nossa Anacor.

Eu poderia detalhar cada uma das variáveis, mas acho que o artigo ficaria muito longo. Se tiver interesse, entre em contato e posso passar o material base deste estudo.

  

### Vamos para a análise!

O primeiro passo foi analisar se temos alguma associação estatisticamente significativa entre as variáveis em geral em relação ao nível de obesidade das nossas observações.

Tivemos, ao final, 16 tabelas de contingência para calcular a estatística qui-quadrado e o p-valor.

Em todas as 16 tabelas, tivemos um p-valor de 0, o que nos permitiu, com um nível de significância de 5%, rejeitar H0 e aceitar H1, onde todas as variáveis possuem associação significativa com a variável do grau de obesidade.

Com 56 categorias e 17 variáveis, temos 39 dimensões possíveis para o nosso cálculo. Mas no final, decidi arbitrariamente elaborar nossa análise com duas dimensões, o que se mostrou suficiente.

O próximo passo foi obter as coordenadas padrão para fazer nosso mapa perceptual.

O primeiro pensamento que tive ao ver o mapa foi: “que bagunça”. Com todas as variáveis e suas categorias, temos muitos pontos no mapa, resultando em um amontoado de informações que dificulta a análise devido à sobreposição dos pontos.

Algumas conclusões poderiam ser tiradas, mas eu gostaria de fazer uma análise mais focada em algumas variáveis específicas.

![](https://media.licdn.com/dms/image/v2/D4D12AQEReVa845bzyw/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616237856?e=1734566400&v=beta&t=kH1jFMCK62RDl5e6sEAauGDBPnP5HV5iGAeXdpERgAw)

  

### Dando alguns passos para trás

Mesmo podendo utilizar todas as variáveis para a análise, decidi dar alguns passos para trás e definir um novo filtro. Como o p-valor de todos era 0, precisei de outra técnica para acompanhar a estatística qui-quadrado, e assim descobri o V de Cramer.

O V de Cramer ajudou a normalizar o qui-quadrado, deixando a pontuação entre 0 e 1, o que nos ajuda a definir um novo parâmetro para análise. Agora, com valores entre 0 e 1, tenho uma diferenciação mais significativa do que o p-valor e mais precisa que os diferentes valores do qui-quadrado.

O próximo passo foi filtrar e eliminar as variáveis cuja associação com o grau de obesidade era menor que 0,3 de V de Cramer.

![](https://media.licdn.com/dms/image/v2/D4D12AQHo91eNlDurbQ/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1720616258026?e=1734566400&v=beta&t=MU_4rM8oIzmVF63bWsPlCf7yZeh7e-GGlAh2bS_sGFs)

Assim, reduzi consideravelmente as variáveis, resultando em uma melhor visualização do gráfico e permitindo uma associação mais precisa entre as variáveis em relação à obesidade.

![](https://media.licdn.com/dms/image/v2/D4D12AQGToAph1hIYTw/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1720616288942?e=1734566400&v=beta&t=93ELju172tLuOqtxSpKXxzWz9FXnfypdm1QQ3-Qgo5o)

  

### Análise do Mapa Perceptual

![](https://media.licdn.com/dms/image/v2/D4D12AQGrCWiohfKX2w/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616491434?e=1734566400&v=beta&t=VW79b7JmJ6U8IzFstma5NxODMRL0y-plDjrsh1teA6E)

Antes de começar a análise, gostaria de esclarecer alguns pontos importantes para acompanhar minha análise.

Primeiramente, a posição dos pontos no gráfico é meramente ilustrativa e serve apenas para mostrar a proximidade entre as categorias para uma associação. Ou seja, um elemento estar mais acima ou mais à direita do gráfico não significa nada em si.

Outro ponto importante é que toda a análise deve levar em conta sua associação com o grau de obesidade. A relação dos pontos sem considerar o grau de obesidade pode até ser feita, mas a precisão da análise só é garantida tendo o grau de obesidade como foco.

O primeiro ponto de destaque é que o grau de obesidade 3 é muito isolado de todas as outras categorias, ou seja, é um evento que não possui muita associação com as outras categorias, sugerindo que as pessoas com esse grau de obesidade não seguem um padrão fixo.

Entre os graus de obesidade, podemos ver que as pessoas com peso muito baixo, peso baixo e peso normal possuem uma associação muito próxima entre si. Por outro lado, sobrepeso 1, sobrepeso 2 e obesidade 1 possuem uma associação muito forte entre si, com obesidade grau 2 um pouco mais afastada. Como mencionado anteriormente, obesidade grau 3 é extremamente isolada.

![](https://media.licdn.com/dms/image/v2/D4D12AQGKcgbglYtsag/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616307576?e=1734566400&v=beta&t=rZ4aTBWzMC8KBnEOfhb8HuQOk_tLWbfh5I0xyjwxy0s)

Com relação à idade, podemos ver que os mais jovens tendem a estar mais próximos do peso ideal, enquanto as idades médias estão mais perto do sobrepeso e obesidade 1. Já os mais velhos estão associados a obesidade grau 2.

Essa associação nos permite entender que, sim, quanto mais jovem a pessoa, mais facilidade ela tem de estar no peso ideal, talvez dando mais prioridade ao cuidado próprio. Conforme as pessoas envelhecem, fica mais difícil manter o peso ideal, aumentando a tendência de entrar em algum grau de obesidade.

![](https://media.licdn.com/dms/image/v2/D4D12AQFTq6zNiPqkDw/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616326504?e=1734566400&v=beta&t=1rXiggpBF_3Ig594cKdV_iKazNG5XGH-NWJ59o6Xs4I)

Os homens têm uma associação forte com o sobrepeso e obesidade grau 1, enquanto as mulheres não possuem associação significativa com nenhum grau de obesidade. Talvez isso indique que as mulheres se cuidam mais que os homens no geral.

![](https://media.licdn.com/dms/image/v2/D4D12AQHLB_23c3J2Ng/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616348483?e=1734566400&v=beta&t=1EqxyoKYUprgCshNpeN6NX9rsNx7SSFzsSqp9uldFNE)

Agora temos uma associação que pode ser confusa: a relação entre peso e obesidade. Por que temos uma associação entre peso e obesidade se elas obviamente estão associadas e são praticamente a mesma coisa?

Temos que considerar que muitas pessoas são musculosas, e músculo pesa mais que gordura. Então, poderíamos ter pessoas pesadas, mas sem sobrepeso ou obesidade. Porém, não é o caso aqui. As pessoas mais leves estão entre os graus sem obesidade, enquanto as pessoas com peso médio estão no sobrepeso ou obesidade grau 1. Isso sugere que mesmo pessoas teoricamente no peso médio podem ser sedentárias e ter pouca massa magra, sendo mais propensas à obesidade.

![](https://media.licdn.com/dms/image/v2/D4D12AQG5bOAxQE1t5Q/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616374682?e=1734566400&v=beta&t=UGo3x6HKFyUABWMtP2NSpn8AphkHR7q1IHD6hiZT6BY)

O FAVC (frequência de consumo de alimentos calóricos) mostra que pessoas no peso ideal não consomem alimentos muito calóricos, enquanto aquelas que consomem estão mais próximas do sobrepeso e obesidade.

![](https://media.licdn.com/dms/image/v2/D4D12AQEx7lZ7NDMjHA/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616396402?e=1734566400&v=beta&t=BJIN4k1hQvH0l65ZrYL701tCBIwbguLxBS6zmc9JQMQ)

O FCVC (frequência de consumo de vegetais) apresenta uma associação interessante. Pessoas que consomem vegetais frequentemente não têm uma associação significativa com o peso ideal e sem obesidade. Aqueles que consomem vegetais algumas vezes estão mais propensos ao sobrepeso e obesidade grau 1. Isso sugere que não há uma relação clara entre consumo de vegetais e peso ideal, ou que nossos dados não são tão precisos.

![](https://media.licdn.com/dms/image/v2/D4D12AQHxb7EV3QVLPg/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616406215?e=1734566400&v=beta&t=IJye4TTm7xQWEoPUTrU2Sbl8RFVtCo0KG5Dh07YSYPc)

A próxima associação é muito interessante: ter familiares acima do peso faz diferença para pessoas em forma e saudáveis. Pessoas com familiares com sobrepeso ou obesidade tendem a estar no mesmo grupo. Isso sugere que a educação alimentar e de vida saudável desde a infância pode levar a uma vida adulta mais saudável.

![](https://media.licdn.com/dms/image/v2/D4D12AQF0TvYasKqh0w/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616431288?e=1734566400&v=beta&t=C2IfE6UQZWXLIFaZJ0VZUjsFKvNtf8GUhakXpD3fsZQ)

O CAEC (consumo de alimentos entre as refeições) mostra que pessoas que sempre se alimentam entre as refeições são mais saudáveis. Essas pessoas provavelmente têm uma relação mais saudável com a comida e, por comerem em porções menores, tendem a exagerar menos e ter uma vida mais saudável.

![](https://media.licdn.com/dms/image/v2/D4D12AQFfI_O8NQWfdg/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616443710?e=1734566400&v=beta&t=wLUQfUg3o1xa4BYEegY6MRobKejaeRKWnpVWkZJgNqQ)

Essas são as associações permitidas pelos dados fornecidos. Mesmo filtrando várias variáveis, ainda temos muita informação para analisar. Vamos juntar todas essas associações em uma conclusão!

  

### Concluindo

Podemos entender com a Análise de Correspondência que as pessoas mais jovens tendem a ser mais saudáveis que as mais velhas. As pessoas mais saudáveis são aquelas que se alimentam melhor, comendo de forma equilibrada e evitando alimentos muito calóricos. Isso pode ser devido à influência de familiares mais saudáveis, que ensinam uma relação melhor com a comida.

O grupo de pessoas com sobrepeso e obesidade grau 1 está associado a homens e pessoas de idade média. Essas pessoas consomem alimentos mais calóricos e têm familiares menos saudáveis, o que influencia seu estilo de vida. Ao contrário das associações das pessoas saudáveis, não diria que as associações das pessoas com sobrepeso e obesidade grau 1 são tão claras entre si. Acredito que individualmente temos uma associação entre as categorias e os graus de sobrepeso.

Pessoas com obesidade grau 2 estão fortemente associadas a uma idade mais avançada, talvez devido à dificuldade em manter um peso saudável com o passar dos anos.

Enquanto isso, obesidade grau 3 não possui associação com nenhuma variável específica, indicando que pessoas nesse grau de obesidade não precisam ter características específicas para estarem nesse estado.

  

### Bônus!

Além do Mapa Perceptual, também podemos plotar um gráfico bem interessante : O mapa de observações, onde podemos ver a posição de cada uma das observações e sua exata categoria de obesidade dentro do gráfico

![](https://media.licdn.com/dms/image/v2/D4D12AQEeAZ2LS1__gA/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1720616522945?e=1734566400&v=beta&t=u-83Td-Fk3zkVTq_S2UAgEqvBTdemILJjmqoBAT3_b8)

Como podemos ver temos mais a direita as pessoas mais saudáveis indo para esquerda para as menos saudáveis, mas essa transição é de forma bem mesclada, enquanto isolado lá em cima na esquerda podemos ver isolado as pessoas com a obesidade grau 3, nos mostrando mais uma vez a falta de associação dela com as outras categorias

Bom! este foi um exercício focado em análise e foi muito interessante de realizar! O material do MBA, em conjunto com pesquisas externas, me ajudou a obter uma visão abrangente sobre Anacor.

Espero que tenham gostado! Até a próxima!