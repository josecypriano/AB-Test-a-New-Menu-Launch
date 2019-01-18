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

## Passo 1: planeje sua análise
Para executar a análise correta, você precisará preparar um conjunto de dados. (Limite de 250 palavras)
Responda às seguintes perguntas para ajudá-lo a planejar sua análise:

1.	Qual é a métrica de desempenho que você usará para avaliar os resultados de seu teste?
2.	Qual é o período de teste?
3.	Em que nível (dia, semana, mês, etc.) os dados devem ser agregados?

## Passo 2: Limpe os Dados 
Nesta etapa, você deve preparar os dados para as etapas 3 e 4. Você deve agregar os dados de transação para o nível apropriado e filtrar nos intervalos de dados apropriados. Você pode assumir que não há dados ausentes, incompletos, duplicados ou sujos. Você está pronto para passar para a próxima etapa quando tiver dados de transações semanais para todas as lojas.

## Passo 3: Combinar Unidades de Tratamento e Controle
Nesta etapa, você deve criar as variáveis de tendência e sazonalidade e usá-las juntamente com outras variáveis de controle para combinar duas unidades de controle a cada unidade de tratamento. 

Nota: Calcule o número de transações por loja por semana para calcular a tendência e a sazonalidade.

Além da tendência e sazonalidade ...

1.	Que variáveis de controle devem ser consideradas? Observação: Considere apenas variáveis no arquivo RoundRoastersStore.
2.	Qual é a correlação entre cada variável de controle potencial e sua métrica de desempenho?
3.	Que variáveis de controle você usará para combinar lojas de tratamento e controle?

Preencha a tabela abaixo com seus pares de lojas de tratamento e controle:

## Etapa 4: Análise e Escrita
Conduza sua análise A / B e crie um breve relatório descrevendo seus resultados e recomendações. (Limite de 250 palavras)

Responda estas perguntas. Certifique-se de incluir visualizações da sua análise:

1.	Qual é a sua recomendação - A empresa deve lançar o menu atualizado para todas as lojas?
2.	Qual é o aumento (lift) do novo menu para as regiões Oeste e Central (incluir significância estatística)?
3.	Qual é o aumento (lift) do novo menu em geral?
