# Estratégia para Preenchimento de Falhas usando Deep Learning e Análise do Potencial Eólico atraves da Distribuicão de Weibull - CCD 2019

## Introdução

Analisando a base de dados, notou-se um problema e uma oportunidade: o problema das falhas existentes nas séries e a oportunidade de gerar um relatório sobre à viabilidade de exploração de energia eólica.

Problemas de séries meteorológicas podem ser modelados através de redes neurais artificiais\cite{araujoaproximaccao}. O presente trabalho usou um modelo de rede recorrente para preencher dados faltantes na base de dados, permitindo uma estimativa robusta para os dados inexistentes. Além disso, com a produção eólica instalada no Brasil e o enorme potencial ainda inexplorado, utilizou-se também os dados para analisar o potencial para produção de energia eólica.

## Preenchimento de falhas nos dados sobre velocidade do vento

Utilizando Long Short-Term Memory (LSTM), modelou-se o problema de estimativa de velocidade do vento para um dado dia, através de informações existentes para os 2 dias anteriores e o dia corrente, aplicando análise PCA para reduzir a dimensionalidade. Para tal, selecionou-se aleatoriamente uma cidade para cada Estado, gerando falhas artificiais e verificando se a rede neural conseguia estimar estes dados para ela desconhecidos.

Como resultado geral, usando uma estimativa com coeficiente de confiança de 0.95, obteve-se uma estimativa com erro médio absoluto de 0.33 +/- 0.06 m/s e coeficiente de correlação R = 0.78 +/- 0.038.

## Análise estatística da velocidade do vento com distribuição de Weibull

A Distribuição Estatística Weibull é um método comum para analisar medições de velocidade do vento e determinar o potencial de produção de energia eólica. Neste trabalho essa distribuição com 2 parâmetros é utilizada para calcular a velocidade de vento mais provável (VMP) e velocidade de vento que carrega mais energia (VMaxE), e a média e mediana da velocidade do vento. Os parâmetros referidos foram calculados utilizando-se a biblioteca Python Weibull, e posteriormente aplicados às funções de velocidade.

Decidiu-se utilizar a VMP e VMaxE como critério de ranqueamento das cidades brasileiras. As melhores pela VMP foram Macau/RN, Mata Grande/AL e Campos Sales/CE, e pela VMAxE, Santa Cruz/RJ, Cabo Frio/RJ e Porto de Pedras/AL. Os valores dos dados do percentil 95-99 para a VMP ficaram entre 3.44m/s e 4.15m/s, e do percentil 99-100, entre 4.17m/s e 5.63m/s. Já para o percentil 95-99 da VMaxE, esses valores situaram-se entre 5.25m/s e 6.58m/s e do percentil 99-100, entre 6.58m/s e 8.57m/s. As cidades destaque na análise se situam nas regiões Nordeste e Sudeste do país.

## Conclusão

Os resultados do preenchimento de falhas indicaram bastante eficiência do modelo utilizado, com uma taxa de erro relativamente baixa e uma correlação forte, tornando uma solução escalável que pode inclusive ser testada para outras séries na mesma base de dados. 

Quanto ao relatório de potenciais eólicos, foi possível se ter uma melhor clareza, dentre os inúmeros dados disponíveis, sobre quais as cidades e regiões mais propícias a serem utilizadas como fonte de geração de energia eólica no país, contribuindo com bons indícios de onde o investimento nesse tipo de fonte de energia devem ser feitos.
____________________________________________________________________________________

Para referências checar o relatório completo.

Link para base de dados:
https://drive.google.com/drive/folders/1GGsegrcqv7NM92FqXcKFAe6eZDXLUcZu?usp=sharing
