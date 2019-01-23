# AB-Test-a-New-Menu-Launch
Project 4 - ND Predictive Analysis for Business


## O Problema do negócio
Round Roasters é uma luxuosa franquia de cafés presente na costa oeste dos Estados Unidos da América. Os últimos anos representaram na estagnação no crescimento da franquia, e uma nova equipe de gestão foi montada para realavancar o crescimento de suas lojas.

A primeira grande iniciativa de crescimento é introduzir sanduíches "gourmet" no cardápio, juntamente de uma carta de vinhos. A nova gestão crê que uma campanha de propagandas televisivas seja crucial para direcionar o público para as lojas com estas novas ofertas.

Contudo, esta campanha publicitária por meio da televisão requeriria um significativo aumento no orçamento de marketing da empresa, com um retorno de investimento (ROI, do inglês Return of Investiment). Ademais, existe uma preocupação que os atuais clientes não iriam aderir aos novos produtos do cardápio.

Para minimizar o risco, a gestão decidiu verificar tais mudanças em duas cidades com novas propagandas televisivas. Denver e Chicago foram as cidades escolhidas para participar desde teste pois o comportamento das lojas (e seus respectivos mercados), são similares aos comportamentos das lojas do restante da rede. Deste modo, a performance obtida nestes mercados pode ser um bom indicativo de como o novo cardápio atuará no restante da cadeia.

O teste fui executado em um período de 12 semanas (entre 29 de Abril de 2016 até 21 de Julho de 2016), onde cinco lojas nos mercados supracitados utilizavam o cardápio atualizado juntamente da campanha publicitária na televisão. A semana fiscal para a cadeia Round Roasters começa na Sexta-feira e termina na Quinta-feira.

O período de comparação é o mesmo do período de testes, menos para o ano passado (29-04-2015 a 21/07/2015).

Você foi requisitado para analizar os resultados do experimento para determinar se a mudança do cardápio deve ser replicada para todas as lojas da franquia. O impacto previsto nas vendas deve ser grande o suficiente para justificar o aumento nos gastos em marketing: um aumento de pelo menos 18% de aumento nas vendas no período de comparação em relação às lojas de controle deve existir, caso contrário, possíveis aumentos serão considerados apenas aumentos incrementais das vendas.

Você teve acesso a três conjuntos de dados para sua análise:

Dados de transações para todas as lojas entre 21 de Janeiro de 2015 até 18 de Agosto de 2016
Uma listagem de todas as lojas Round Roasters
A listagem de 10 lojas (5 em cada mercado) que foram utilizadas como mercados teste.

## Passo 1: Planeje sua análise
Para executar a análise correta, você precisará preparar um conjunto de dados. (Limite de 250 palavras)
Responda às seguintes perguntas para ajudá-lo a planejar sua análise:

1.	Qual é a métrica de desempenho que você usará para avaliar os resultados de seu teste?

A métrica que pode ser usada para a avaliação dos resultados é Gross Margin, pois dá possibilidade de analisar o desempenho das lojas.

2.	Qual é o período de teste?

O período de testes foi de 12 semanas, de 29-abr-16 à 21-jul-16.

3.	Em que nível (dia, semana, mês, etc.) os dados devem ser agregados?

Os dados serão agregados em semanas, visto que os clientes visitam as lojas pelo menos uma vez por semana.

## Passo 2: Limpe os Dados 
Nesta etapa, você deve preparar os dados para as etapas 3 e 4. Você deve agregar os dados de transação para o nível apropriado e filtrar nos intervalos de dados apropriados. Você pode assumir que não há dados ausentes, incompletos, duplicados ou sujos. Você está pronto para passar para a próxima etapa quando tiver dados de transações semanais para todas as lojas.

Neste workflow, foi selecionado apenas as 76 semanas necessárias para a criação dos resultados, além da inclusão de campos como *week, week_start, week_end e new_product_flag*. A partir disso, foi criado os arquivos de *weekly_store_traffic, weekly_store_sale e store_list* que serão necessários para a continuação das estimativas.

![01 - alteryx data clean up flow](https://user-images.githubusercontent.com/34245933/51574718-25d2a400-1e96-11e9-8cae-fce0fcc8d5cb.PNG)
*Figura 1: Workflow para Limpar os Dados*


## Passo 3: Combinar Unidades de Tratamento e Controle
Nesta etapa, você deve criar as variáveis de tendência e sazonalidade e usá-las juntamente com outras variáveis de controle para combinar duas unidades de controle a cada unidade de tratamento. 

Nota: Calcule o número de transações por loja por semana para calcular a tendência e a sazonalidade.

Além da tendência e sazonalidade ...

1.	Que variáveis de controle devem ser consideradas? Observação: Considere apenas variáveis no arquivo RoundRoastersStore.

Quando fazer a limpeza dos dados, exclusão de colunas que não serão importantes, ficamos com um total de 20 variáveis, dentro das quais 2 delas podem ser variáveis de controle: *AvgMonthSales* e *Sq_Ft*.

2.	Qual é a correlação entre cada variável de controle potencial e sua métrica de desempenho?

Analisando a correlação das variáveis de controle com a métrica de desempenho,*Gross.Margin*, percebemos que a varíavel *AvgMonthSales* tem uma alta correlação com a métrica de desempenho, de *0.990*, enquanto *Sq_Ft* tem uma baixíssima correlação, de *-0.024*. Como podemos ver na figura abaixo:

![02 - pearson correlation](https://user-images.githubusercontent.com/34245933/51574841-b6a97f80-1e96-11e9-8f21-b47af48bf443.PNG)
*Figura 2: Pearson Correlation Analysis*

3.	Que variáveis de controle você usará para combinar lojas de tratamento e controle?

Usaremos a variável *AvgMonthSales*, como variável controle. Além das variáveis que serão escolhidas pela ferramenta *AB Trend*.

Preencha a tabela abaixo com seus pares de lojas de tratamento e controle:

![03 - treatment and control stores](https://user-images.githubusercontent.com/34245933/51604292-7a583c80-1ef3-11e9-90b7-952401005c0e.png)  
*Figura 3: Lojas Treatment e Control*

## Etapa 4: Análise e Escrita
Conduza sua análise A / B e crie um breve relatório descrevendo seus resultados e recomendações. (Limite de 250 palavras)

Responda estas perguntas. Certifique-se de incluir visualizações da sua análise:

1.	Qual é a sua recomendação - A empresa deve lançar o menu atualizado para todas as lojas?

Recomendaria fortemente à empresa lançar o novo menu para todas as lojas. Essa recomendação é com base que o nosso Teste AB sinalizou um aumento na nossa *Gross.Margin* maior que os 18% estabelecido pela empresa. O nosso teste mostrou que aumentaríamos o *Gross.Margin* em aproximadamente 40.1%.

2.	Qual é o aumento (lift) do novo menu para as regiões Oeste e Central (incluir significância estatística)?

O aumento (lift) para a região *West* é de 35.4% enquanto para região *Central* é de 44.7% com significância de 99.4% e 99.6% respectivamente. Com isso podemos dizer que temos uma grande change, estatisticamente falando, que estes números estão acurados. Podemos ver os resultados nos gráficos abaixo.

### West Analysis
![04 - west analaysis](https://user-images.githubusercontent.com/34245933/51605951-a83f8000-1ef7-11e9-9895-8ca5f3d9b7cf.PNG)
*Figura 4: West Analysis*

### Central Analysis
![05 - central analysis](https://user-images.githubusercontent.com/34245933/51605964-aecdf780-1ef7-11e9-8257-601ccf6563b3.PNG)
*Figura 5: Central Analysis*

3.	Qual é o aumento (lift) do novo menu em geral?

O aumento (lift) do novo menu em geral é de 40.1% com significância de 100%. Podemos dizer que temos uma grande change, estatisticamente falando, que estes números estão acurados. Podemos ver os resultados nos gráficos abaixo.

### Overall Analysis
![06 - overall analysis](https://user-images.githubusercontent.com/34245933/51605729-061f9800-1ef7-11e9-981d-b61ca8fc9cf4.PNG)
*Figura 6: Overall Analysis*

## Alteryx Flow

![07 - alteryx treatment control](https://user-images.githubusercontent.com/34245933/51606288-a4602d80-1ef8-11e9-98b5-0cb6020aef19.PNG)
*Figura 7: Treatment Workflow*

![08 - alteryx ab analysis](https://user-images.githubusercontent.com/34245933/51606324-bb9f1b00-1ef8-11e9-94c7-da4dd08f1ed2.PNG)  
*Figura 8: AB Analysis Workflow*

