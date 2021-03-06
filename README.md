# Health Insurance Cross-Sell

# Insurance All Company

**Aviso:** O seguinte contexto é completamente fictício, a empresa, o contexto, o CEO, as questões de negócios existem apenas na minha imaginação.

A Insurance All é uma empresa que oferece seguro saúde para seus clientes e a equipe de produtos está analisando a possibilidade de oferecer aos segurados um novo produto: o seguro de automóveis.

Tal como acontece com o seguro saúde, os clientes deste novo plano de seguro de automóveis precisam pagar um valor anualmente à Insurance All para obter um valor segurado pela empresa, destinado a custear um eventual sinistro ou dano ao veículo.

A Insurance All conduziu uma pesquisa com cerca de 380.000 clientes sobre seu interesse em ingressar em um novo produto de seguro de automóveis no ano passado. Todos os clientes manifestaram interesse ou não em adquirir seguro de automóveis e essas respostas foram salvas em um banco de dados junto com outros atributos do cliente.

A equipe de produtos selecionou 127 mil novos clientes que não responderam à pesquisa para participar de uma campanha, na qual receberão a oferta do novo produto de seguro de automóveis. A oferta será feita pela equipe de vendas por meio de ligações telefônicas.

Porém, a equipe de vendas tem capacidade para realizar 20 mil ligações no período da campanha.

# Problema de Negócio

Nesse contexto, você foi contratado como consultor de Data Science para construir um modelo que prevê se o cliente estaria ou não interessado em seguro de automóveis.
Com a solução, a equipe de vendas espera poder priorizar as pessoas com maior interesse no novo produto e, assim, otimizar a campanha fazendo apenas contatos com os clientes mais propensos a realizar a compra.
Como resultado de sua consultoria, você precisará entregar um relatório contendo algumas análises e respostas para as seguintes perguntas:

	- Principais insights sobre os atributos mais relevantes dos clientes interessados em adquirir seguro de automóveis.
	- Que porcentagem de clientes interessados em comprar seguro de automóveis a equipe de vendas poderá atingir com 20.000 ligações?
	- E se a capacidade da equipe de vendas aumentar para 40.000 chamadas, que porcentagem de clientes interessados em adquirir seguro de automóveis a equipe de vendas poderá entrar em contato?
	- Quantas ligações a equipe de vendas precisa fazer para contatar 80% dos clientes interessados em adquirir seguro de automóveis?

Os Dados do conjunto estão disponível em um banco de dados Postgresql e cada linha representa um cliente e cada coluna contém alguns atributos que descrevem aquele cliente, além de sua resposta à pesquisa, na qual ela mencionou interesse ou não no novo produto de seguro.

# Planejamento da Solução

## Qual é a solução?

É necessário desenvolver um modelo de aprendizado de máquina que classifique os clientes com base em sua probabilidade de aquisição de seguro de veículos.

## Como será a solução?

Este Modelo estará disponível em uma API, podendo ser utilizado pelo cliente a qualquer momento que ele precise.

## Hospedagem

A API será hospedada na plataforma Heroku e está disponível neste url: https://health-insurance-predition-rbp.herokuapp.com.

# Estratégia da Solução

Minha estratégia para solucionar este problema foi:

**Etapa 01. Descrição dos dados: Meu objetivo é usar métricas estatísticas para identificar dados fora do escopo do negócio.**

**Etapa 02. Feature Engineering: Derive novos atributos com base nas variáveis originais para descrever melhor o fenômeno que será modelado.**

**Passo 03. Filtragem de Dados: Filtre linhas e selecione colunas que não contenham informações para modelagem ou que não correspondam ao escopo do negócio.**

**Etapa 04. Análise exploratória de dados: Explore os dados para encontrar insights e entender melhor o impacto das variáveis no aprendizado do modelo.**

**Etapa 05. Preparação dos dados: Prepare os dados para que os modelos de aprendizado de máquina possam aprender o comportamento específico.**

**Etapa 06. Seleção de recursos: Seleção dos atributos mais significativos para treinar o modelo.**

**Etapa 07. Machine Learning Modelling: treinamento do modelo de aprendizado de máquina**

**Etapa 08. Hyperparameter Fine Tunning: Escolha os melhores valores para cada um dos parâmetros do modelo selecionado na etapa anterior.**

**Etapa 09. Conversão do desempenho do modelo em valores de negócios: Converta o desempenho do modelo em um resultado de negócios.**

**Etapa 10. Deploy Model to Production: Publique o modelo em um ambiente de nuvem para que outras pessoas ou serviços possam usar os resultados para melhorar a decisão de negócios.**

**Etapa 11. Previsão por Google Sheets: Criação de uma planilha no Google Sheets com um botão de previsão do modelo.**

# Modelos de Machine Learning Aplicados

Os Testes foram realizados usando os seguintes algoritmos:

**KNN Classifier**

**Logistic Regression**

**Random Forest**

**Extra Trees**

# Conclusões

Ao Final deste projeto foi possivel compreender o fenômeno Learning to Rank (LTR) e como é utilizada usada para aperfeiçoar os resultados da pesquisa com base em coisas como padrões de uso reais. Existem três abordagens para LTR sendo elas Pointwise,Listwise e Pairwise (utilizada neste projeto).

Abordagens de Pairwise examinam dois documentos juntos. Eles também usam classificação ou regressão - para decidir qual dos pares tem melhor classificação.

Comparamos este par superior-inferior com a verdade básica e ajustamos a classificação se não corresponder. O objetivo é minimizar o número de casos em que o par de resultados está na ordem errada em relação à verdade fundamental.
Outro ponto interessante foram as métricas diferenciadas para este tipo de metodologia, onde se utilizam as denominadas metricas @K/atK, diferente das métricas de avaliação padrões, as métricas TOPK (@K/atK) estão interessados em ranquear os N itens principais. Portanto, faz mais sentido calcular a precisão e recuperar as métricas nos primeiros N itens em vez de em todos os itens. Assim, a noção de precisão e rechamada em k, onde k é um número inteiro definível pelo avaliador para corresponder ao objetivo das N recomendações principais.

# Próximos Passos

Iniciar mais um ciclo para analisar o problema buscando abordagens diferentes, tendo em vista principalmente o desbalanceamento do conjunto de dados.

Possíveis pontos para serem abordados no segundo ciclo:

-Aprofundamento em derivações de features

-Rescaling e Encode dos dados com metodologias diferentes

-Trabalhar com novas Features para treinar o modelo

-Trabalhar com um método mais robusto para achar os melhores Hyperparametros para o modelo
