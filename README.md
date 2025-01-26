# Interpretabilidade de modelos

Este repositório tem como objetivo apresentar, estudar e dissertar sobre interpretabilidade de modelos. A ideia não é trazer todo embasamento teórico, mas sim deixar o mais claro possível alguns métodos dentro dessa área. Antes de iniciar sobre os temas específicos, alguns comentários serão feitos para que haja alinhamento de pensamentos.

# Definição

O que é um modelo de Machine Learning (ML), estatístico ou modelo de Inteligência Artificial (IA)? A procura de explicações de um evento de interesse, denotado por $Y$, presume-se a existência de relações entre $Y$ e outras características/variáveis, estas denotadas por $X$. A composição entre $Y$ e $X$ pode ser expressa como $Y = f(X) + \epsilon$, em que $\epsilon$ representa um erro aleatório não correlacionado com $X$ e o montante não explicado pela relação $f(X)$. Tal composição pode ser entendida como uma representação de modelo de ML, modelo estatístico ou modelo de IA.

Na realidade, procura-se estimar a relação de $Y$ e $X$ como $\hat{Y} \approx \hat{f}(X)$, uma vez que não é possível conhecer todas as variáveis (e suas relações $f(.)$) que expliquem o evento de interesse $Y$. Assim, espera-se encontrar um estimador $\hat{Y}$ que seja o mais representativo possível de Y.

# Para que serve um modelo

O objetivo de um modelo é capturar relações complexas entre $Y$ e $f(X)$ e, por exemplo, em conjunto com uma estratégia de negócio otimizar receitas e despesas. Por exemplo: na fase final de recuperação de crédito, em geral, quanto maior os dias em atraso ou o saldo em atraso menor a chance de um cliente pagar sua dívida. Com a aplicação de um modelo de ML, observa-se também que o grupo de inadimplentes com menor chance de pagar a dívida reduziu o share de crédito com a instituição financeira nos últimos 3 meses, concentram-se em um público mais jovem (com pouco histórico de crédito) e localizado em uma região metropolitana.

Observação: dependendo do cenário da empresa (considere a maturidade analítica: governança de dados, indicadores, modelos de ML, etc), algumas análises de dados em conjunto com o time de negócios podem provocar algumas hipóteses que podem ser testadas e validadas sem a necessidade da construção, monitoramento e manutenção de um Sistema de Machine Learning.

# Por que o resultado do modelo foi esse?

Antes de entender a relação do resultado do modelo $\hat{Y}$ com $X$, é importante ter uma fase de diagnóstico do modelo, mesmo que de forma simplificada, principalmente, para os modelos estatísticos que exigem pressuposições. Alguns exemplo são: as probabilidades estão aderentes? O Brier Score está próximo ou abaixo da média da variável target ($\bar{y}$)? Como está o valor da log-loss? Como ficou o gráfico de calibração? Como ficaram as distribuições dos resíduos ($r~i~ = y_{i} - \hat{y}_{i}$) e dos valores estimados ($\hat{y}_{i}$)? Como está o erro de regressão?

Em algum momento, haverá o interesse em entender qual é o impacto de algumas variáveis na resposta estimada pelo modelo. Por que o modelo calculou uma alta/baixa probabilidade de default (não ficar em dia em um contrato de crédito) para o cliente A? Quais são as variáveis que impactam no aumento/redução do preço de um imóvel? Quais variáveis são responsáveis pela alta/baixa probabilidade de uma pessoa ter um AVC? É possível alterar algumas variáveis para que a resposta ($\hat{y}$) seja diferente?

As respostas para essas perguntas podem ser obtidas pela área de interpretabilidade de modelos.

# Definição
