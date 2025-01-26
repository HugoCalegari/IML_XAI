# Interpretabilidade de modelos

Este repositório tem como objetivo apresentar, estudar e dissertar sobre interpretabilidade de modelos. A ideia não é trazer todo embasamento teórico, mas sim deixar o mais claro possível alguns métodos dentro dessa área. Antes de iniciar sobre os temas específicos, alguns comentários serão feitos para que haja alinhamento de pensamentos.

# Defnição

O que é um modelo de Machine Learning (ML), estatístico ou modelo de Inteligência Artificial (IA)? A procura de explicações de um evento de interesse, denotado por Y, presume-se a existência de relações entre Y e outras características/variáveis, estas denotadas por X. A composição entre Y e X pode ser expressa como $Y = f(X) + \epsilon$, em que $\epsilon$ representa um erro aleatório não correlacionado com X e o montante não explicado pela relação $f(X)$. Tal composição pode ser entendida como uma representação de modelo de ML, modelo estatístico ou modelo de IA.

Na realidade, procura-se estimar a relção de Y e X como $\hat{Y} = \hat{f}(X)$.
