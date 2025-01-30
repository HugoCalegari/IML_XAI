# Interpretabilidade de modelos

Este repositório tem como objetivo apresentar, estudar e dissertar sobre interpretabilidade de modelos (também conhecida como Interpretable Machine Learning (IML) ou eXplainable AI (XAI)). É um novo campo que visa tornar o modelo mais compreensível e socialmente aceito. Esta última parte, é muito importante, principalmente, na etapa de convencimento da escolha do modelo e sua aplicação. A ideia não é trazer todo embasamento teórico, mas sim deixar o mais claro possível alguns métodos dentro dessa área. Antes de iniciar sobre os temas específicos, alguns comentários serão feitos para que haja alinhamento de pensamentos.

# Definição

O que é um modelo de Machine Learning (ML), estatístico ou modelo de Inteligência Artificial (IA)? A procura de explicações de um evento de interesse, denotado por $Y$, presume-se a existência de relações entre $Y$ e outras características/variáveis, estas denotadas por $X$. A composição entre $Y$ e $X$ pode ser expressa como $Y = f(X) + \epsilon$, em que $\epsilon$ representa um erro aleatório não correlacionado com $X$ e o montante não explicado pela relação $f(X)$. Tal composição pode ser entendida como uma representação de modelo de ML, modelo estatístico ou modelo de IA.

Na realidade, procura-se estimar a relação de $Y$ e $X$ como $\hat{Y} \approx \hat{f}(X)$, uma vez que não é possível conhecer todas as variáveis (e suas relações $f(.)$) que expliquem o evento de interesse $Y$. Assim, espera-se encontrar um estimador $\hat{Y}$ que seja o mais representativo possível de Y.

# Para que serve um modelo

O objetivo de um modelo é capturar relações complexas entre $Y$ e $f(X)$ e, por exemplo, em conjunto com uma estratégia de negócio otimizar receitas e despesas. Por exemplo: na fase final de recuperação de crédito, em geral, quanto maior os dias em atraso ou o saldo em atraso menor a chance de um cliente pagar sua dívida. Com a aplicação de um modelo de ML, observa-se também que o grupo de inadimplentes com menor chance de pagar a dívida reduziu o share de crédito com a instituição financeira nos últimos 3 meses, concentram-se em um público mais jovem (com pouco histórico de crédito) e localizado em uma região metropolitana.

Observação: dependendo do cenário da empresa (considere a maturidade analítica: governança de dados, indicadores, modelos de ML, etc), algumas análises de dados em conjunto com o time de negócios podem provocar algumas hipóteses que podem ser testadas e validadas sem a necessidade da construção, monitoramento e manutenção de um Sistema de Machine Learning.

# Por que o resultado do modelo foi esse?

Antes de entender a relação do resultado do modelo $\hat{Y}$ com $X$, é importante ter uma fase de diagnóstico do modelo, mesmo que de forma simplificada, principalmente, para os modelos estatísticos que exigem pressuposições. Alguns exemplo são: as probabilidades estão aderentes? O Brier Score está próximo ou abaixo da média da variável target ($\bar{y}$)? Como está o valor da log-loss? Como ficou o gráfico de calibração? Como ficaram as distribuições dos resíduos ($ri = yi - \hat{y}i$) e dos valores estimados ($\hat{y}i$)? Como está o erro de regressão?

Em algum momento, haverá o interesse em entender qual é o impacto de algumas variáveis na resposta estimada pelo modelo. Por que o modelo calculou uma alta/baixa probabilidade de default (não ficar em dia em um contrato de crédito) para o cliente A? Quais são as variáveis que impactam no aumento/redução do preço de um imóvel? Quais variáveis são responsáveis pela alta/baixa probabilidade de uma pessoa ter um AVC? É possível alterar algumas variáveis para que a resposta ($\hat{y}$) seja diferente?

As respostas para essas perguntas podem ser obtidas pela área de interpretabilidade de modelos.

# Definição

O que é interpretabilidade de modelos? Interpretabilidade é o "grau" que um modelo pode ser entendido por um ser humano. Pela figura abaixo, nota-se que modelos mais complexos (à direita) tedem a ser menos interpretáveis e com maior acurácia. Modelos menos complexos tendem a ser mais interpretáveis e com menor acurácia. Aqui, acurácia é qualquer métrica que se julga mais interessante para o problema a ser resolvido, ou seja, pode ser a própria acurácia, f1-score, curva ROC, etc.

![image](Representacao1.png 'Grau de interpretabilidade e acurácia do modelo.')

Veja que existem dois grandes blocos de modelos (parte inferior da figura) e uma área de transição (meio da figura). Os modelos interpretáveis são aqueles que podem ser entendidos pelos seres humanos sem a necessidade de nenhum método ou ajuda. Os modelos explicáveis precisam de técnicas ou métodos adicionais para que o modelo seja entendido pelos seres humanos. A área fuzzy (nebulosa) é uma região de transição ou não bem definida de interpretabilidade. Por exemplo: uma árvore de decisão é interpretável desde que sua profundidade seja razoável (torna-se trabalhoso interpretar uma árvore com profundidade de 50!); regressão linear múltipla e logística a interpretação é via coeficientes; floresta aleatória pode cair em um cenário de interpretabilidade, desde que se tenha poucas árvores e com baixa profundidade, ou de baixa interpretabilidade no cenário de muitas (poucas) árvores e com diferentes profundidades (grande profundidade). Veja que o último cenário mostra uma configuração fuzzy: qual é o ponto em que um modelo deixa de ser interpretável para ser explicável?

## Categorizações de IML

Os métodos de interpretabilidade dos modelos podem ser divididos em:

- métodos ou modelos agnósticos (model agnostic): funcionam independente do modelo. Por exemplo: Partial Dependence Plot (PDP), permutation feature, SHapley Additive exPlanations (SHAP), Local Interpretable Model-Agnostic Explanations (LIME) etc.

- métodos ou modelos específicos (model specific): funcionam para modelos específicos ou para uma família de modelos. Por exemplo: SHAP (tree-based, linear models, neural network), etc.

- explicabilidade global: consegue explicar o modelo inteiro e podem se enquadrar em modelos agnósticos ou específicos. Por exemplo: SHAP, PDP, etc.

- explicabilidade local: consegue explicar predições individuais e podem se enquadrar em modelos agnósticos ou específicos. Por exemplo: SHAP, LIME, etc.

Além disso, os métodos podem usar técnicas de permutação ou surrogate models ("modelos interinos" ou "modelos substitutos"). Por exemplo: pode-se considerar que o PDP usa a permutação de variáveis mantida uma constrante e o LIME é um exemplo de método que usa um surrogate model.

# Referências

Livro: 

- https://christophm.github.io/interpretable-ml-book/ 

PDP:

- https://www.youtube.com/watch?v=d3U-B0oXLkc
- https://www.youtube.com/watch?v=dEhbS37Kglc

LIME:

- https://www.youtube.com/watch?v=dQ_jvRkzN1Q
- https://www.youtube.com/watch?v=d6j6bofhj2M
- Paper: https://arxiv.org/pdf/1602.04938

SHAP:

- https://www.youtube.com/watch?v=MQ6fFDwjuco&list=PLqDyyww9y-1SJgMw92x90qPYpHgahDLIK
- https://www.youtube.com/watch?v=9haIOplEIGM
- https://www.youtube.com/watch?v=D8CvcLdy9Nc&list=PLcrc6i6xwaQSw8553tgt1p8XOMFEdQCbl 
- https://www.din.uem.br/sbpo/sbpo2002/pdf/arq0227.pdf
- Paper:  https://arxiv.org/pdf/1705.07874

Contrafactuais:

- https://www.youtube.com/watch?v=UUZxRct8rIk