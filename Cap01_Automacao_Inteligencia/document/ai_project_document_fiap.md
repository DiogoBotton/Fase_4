
<img src="../assets/logo_fiap.jpg" alt="FIAP - Faculdade de Informática e Admnistração Paulista" border="0" width=30% height=30%>

# Sistema de irrigação automático - Fase 4 - Capítulo 1 - FIAP


## Nome do Grupo

#### Nomes dos integrantes do grupo

- Brenner H F Araújo 
- Bryan Fagundes 
- Diogo Botton 
- Hyanka Coelho 
- Juliana Hungaro Fidelis 



## Sumário

[1. Introdução](#c1)

[2. Visão Geral do Projeto](#c2)

[3. Desenvolvimento do Projeto](#c3)

[4. Resultados e Avaliações](#c4)

[5. Conclusões e Trabalhos Futuros](#c5)

[6. Referências](#c6)

[Anexos](#c7)

<br>

# <a name="c1"></a>1. Introdução

## 1.1. Escopo do Projeto

### 1.1.1. Contexto da Inteligência Artificial

A FarmTech Solutions atua no crescente segmento da agricultura de precisão, utilizando a inteligência artificial para otimizar processos agrícolas e aumentar a produtividade. Nossa solução se concentra em desenvolver ferramentas e plataformas que utilizam dados de sensores, imagens de satélite e outras fontes para fornecer insights valiosos aos agricultores. Através da análise desses dados, nossos sistemas podem identificar padrões, prever resultados e recomendar ações personalizadas, como a aplicação precisa de fertilizantes e a otimização da irrigação. Essa abordagem permite que os agricultores maximizem a eficiência de seus recursos, reduzam custos e contribuam para a sustentabilidade do agronegócio. Nosso foco inicial é o mercado brasileiro, onde a agricultura desempenha um papel fundamental na economia, mas vislumbramos expandir nossas operações para outros países da América Latina e, futuramente, para o mercado global.

### 1.1.2. Descrição da Solução Desenvolvida

Utilizando sensores IoT e algoritmos de machine learning, a FarmTech Solutions desenvolveu uma plataforma de agricultura de precisão que transforma dados em insights acionáveis. Através de sensores instalados no campo, coletamos dados em tempo real sobre a umidade do solo e outros parâmetros relevantes para a cultura (fósforo (P) e potássio (K)). Com base nessas informações, nosso sistema ajusta automaticamente a frequência e a duração da irrigação, garantindo que as plantas recebam a quantidade exata de água necessária para um desenvolvimento saudável e otimizando o uso desse recurso essencial.

# <a name="c2"></a>2. Visão Geral do Projeto

## 2.1. Objetivos do Projeto

Este projeto tem como objetivo desenvolver uma solução tecnológica que automatiza o processo de irrigação, tornando-o mais eficiente e preciso. Utilizando sensores e um microcontrolador, o sistema monitora continuamente as condições do solo e aciona a bomba d'água de forma autônoma, adaptando-se às necessidades específicas de cada plantação.

## 2.2. Público-Alvo

Agricultores que buscam uma solução tecnológica para automatizar a irrigação e tomar decisões baseada em dados para gerenciar suas plantações.

## 2.3. Metodologia

**Para este projeto seguimos as etapas abaixo:**

**- Carregamento dos Dados**

Os dados foram carregados a partir de um arquivo CSV denominado produtos_agricolas.csv.

**- Criação de Features**

Foi criada a variável alvo irrigation_on, que indica se a irrigação deve estar ligada ou desligada, com base nas condições de temperatura, umidade e precipitação. Além disso, a coluna label foi renomeada para culture.

**- Análise Exploratória dos Dados**

Foram obtidas informações detalhadas sobre o DataFrame, incluindo o número de entradas e os tipos de dados. Além disso, foi criada uma matriz de correlação para visualizar as relações entre as variáveis.

**- Criação do Pipeline de Pré-processamento e Classificação**

Foi definido um pipeline que inclui a normalização dos dados (MinMaxScaler) e um classificador (RandomForestClassifier).

**- Treinamento do Modelo**

Os dados foram separados em variáveis independentes (X) e a variável dependente (y). Em seguida, o pipeline foi treinado com esses dados.

**- Avaliação da Importância das Variáveis**

Foi extraído o classificador do pipeline e plotada a importância relativa das variáveis para o problema de irrigação automática.

**- Exportação do Modelo**

O pipeline treinado foi exportado para um arquivo .joblib para uso futuro.

# <a name="c3"></a>3. Desenvolvimento do Projeto

## 3.1. Tecnologias Utilizadas

As bibliotecas necessárias foram importadas, incluindo ferramentas para manipulação de dados (pandas), visualização (seaborn e matplotlib), criação de pipelines (sklearn.pipeline), pré-processamento (sklearn.preprocessing), validação cruzada (sklearn.model_selection), classificação (sklearn.ensemble) e serialização de modelos (joblib).

## 3.2. Modelagem e Algoritmos

*Descreva os modelos e algoritmos de IA utilizados no projeto. Explique por que esses modelos foram escolhidos e como foram implementados.*

O principal modelo de IA utilizado neste projeto foi o RandomForestClassifier, que é um algoritmo de aprendizado supervisionado usado para classificação. Ele consiste em um conjunto de árvores de decisão e opera construindo múltiplas árvores durante o treinamento e gerando a classe que é o modo das classes (classificação) ou a média das previsões (regressão) das árvores individuais.


Razões para a Escolha do Modelo

- Robustez e Precisão: O RandomForestClassifier é conhecido por sua alta precisão e robustez. Ele é capaz de lidar com grandes conjuntos de dados e muitas variáveis de entrada sem a necessidade de muita parametrização.

- Resistência ao Overfitting: Devido ao seu processo de construção de múltiplas árvores de decisão e à média dos resultados, o RandomForestClassifier é mais resistente ao overfitting em comparação com uma única árvore de decisão.

- Importância das Variáveis: O algoritmo permite a avaliação da importância das variáveis, o que é crucial para entender quais fatores climáticos são mais influentes na decisão de ligar ou desligar a irrigação.

- Facilidade de Implementação: A implementação do RandomForestClassifier é facilitada pela biblioteca scikit-learn, que oferece uma interface simples e eficiente para o uso de algoritmos de machine learning.

**Implementação**

A implementação do RandomForestClassifier foi realizada através de um pipeline de pré-processamento e classificação. Neste pipeline, o MinMaxScaler é utilizado para normalizar os dados, garantindo que todas as variáveis estejam na mesma escala, o que é importante para o desempenho de muitos algoritmos de aprendizado de máquina.

Para o treinamento do modelo, os dados foram divididos em variáveis independentes (X) e a variável dependente (y). O pipeline foi então treinado com esses dados, ajustando o modelo para prever a necessidade de irrigação.

A avaliação da importância das variáveis permitiu a identificação dos fatores climáticos mais influentes no modelo de decisão.

Após o treinamento, o modelo foi exportado para um arquivo .joblib, permitindo sua reutilização e aplicação futura sem necessidade de re-treinamento.

## 3.3. Treinamento e Teste

Para o desenvolvimento do modelo de irrigação automática, utilizamos um conjunto de dados denominado produtos_agricolas.csv, que contém informações climáticas e outras variáveis relevantes para a irrigação. As principais variáveis incluídas no conjunto de dados são:

- temperature: Temperatura (em graus Celsius)
- humidity: Umidade (em porcentagem)
- rainfall: Precipitação (em milímetros)
- culture: Tipo de cultura
- N, P, K, ph: Nutrientes do solo e pH
- irrigation_on: Variável alvo indicando se a irrigação deve estar ligada (True) ou desligada (False)

**Divisão dos Dados**

Os dados foram divididos em conjuntos de treinamento e teste para avaliar o desempenho do modelo. Utilizamos a função train_test_split da biblioteca scikit-learn para realizar essa divisão, garantindo que o modelo fosse treinado em um subconjunto dos dados e testado em um subconjunto separado.

**Treinamento do Modelo**

O pipeline de pré-processamento e classificação foi feito utilizando o conjunto de treinamento. O pipeline inclui a normalização dos dados (MinMaxScaler) e o classificador (RandomForestClassifier).

**Métricas de Avaliação**

O desempenho do modelo foi avaliado nas principais métricas de avaliação, sendo elas:

- Acurácia: Proporção de previsões corretas em relação ao total de previsões.
- Precisão: Proporção de verdadeiros positivos em relação ao total de positivos preditos.
- Recall: Proporção de verdadeiros positivos em relação ao total de reais positivos.
- F1-Score: Média harmônica entre precisão e recall, proporcionando um equilíbrio entre as duas métricas.

Utilizamos a função classification_report da biblioteca scikit-learn para calcular essas métricas.

**Resultados Obtidos**

Os resultados obtidos com o modelo RandomForestClassifier foram satisfatórios, com boas métricas de acurácia, precisão, recall e F1-score. Os resultados indicam que o modelo tem uma alta capacidade de prever corretamente quando a irrigação deve ser ligada ou desligada, com uma acurácia geral de 95%.

# <a name="c4"></a>4. Resultados e Avaliações

## 4.1. Análise dos Resultados

Analise os resultados obtidos com os modelos de IA. Compare os resultados esperados com os resultados reais e discuta as possíveis razões para as diferenças.

Ao desenvolver o modelo de IA para prever a necessidade de irrigação automática, esperávamos obter um modelo com alta acurácia, que fosse capaz de identificar corretamente quando a irrigação deve ser ligada ou desligada. 

**Expectativas**

- Acurácia superior a 90%.
- Alta Precisão e Recall, especialmente para a classe "True" (irrigação ligada), para garantir que a irrigação não fosse ativada desnecessariamente e que não houvesse falta de irrigação quando necessário.
- Um bom equilíbrio entre precisão e recall, refletido em um alto F1-score, seria ideal para garantir a eficácia do modelo em ambas as classes.

**Realidade**

Os resultados reais mostram que o modelo atingiu uma acurácia de 95%, o que está acima das expectativas iniciais de 90%. A precisão e o recall para a classe "True" (irrigação ligada) também são altos, com valores de 94% e 91%, respectivamente, resultando em um F1-score de 92%. Para a classe "False" (irrigação desligada), a precisão e o recall são ainda mais altos, com valores de 95% e 97%, respectivamente, resultando em um F1-score de 96%.

## 4.2. Feedback dos Usuários

O modelo ainda não foi avaliado pelos usuários.

# <a name="c5"></a>5. Conclusões e Trabalhos Futuros

Os resultados obtidos com o modelo RandomForestClassifier são excelentes e superam as expectativas iniciais. A alta acurácia, precisão, recall e F1-score indicam que o modelo é eficaz em prever a necessidade de irrigação automática. As possíveis razões para as diferenças entre os resultados esperados e reais incluem o desbalanceamento dos dados, a complexidade do modelo, a qualidade dos dados e a importância das variáveis climáticas. No geral, o modelo demonstrou ser uma ferramenta valiosa para a automação da irrigação, proporcionando uma gestão eficiente dos recursos hídricos na agricultura.

**Pontos fortes**
- O modelo RandomForestClassifier apresentou uma acurácia de 95%, indicando uma alta proporção de previsões corretas.
- Devido ao uso de múltiplas árvores de decisão, o modelo é robusto e menos propenso ao overfitting.
- A capacidade do modelo de avaliar a importância das variáveis climáticas fornece insights valiosos para a tomada de decisões agrícolas.
- A utilização da biblioteca scikit-learn facilitou a criação e o treinamento do modelo, bem como a avaliação e a exportação do pipeline.
- Modelo mostrou-se eficaz em generalizar bem nos dados de teste, o que sugere uma boa capacidade de predição em novos dados.

**Pontos a melhorar**
- O conjunto de dados pode estar desbalanceado, com mais exemplos de uma classe em relação à outra, o que pode afetar o desempenho do modelo.
 - Inclusão de variáveis adicionais
- Utilização de técnicas de validação cruzada mais robustas pode ajudar a garantir que o modelo não esteja superajustado aos dados de treinamento.
- Incluir técnicas como SHAP (SHapley Additive exPlanations) para melhorar a explicabilidade detalhada das decisões do modelo

**Plano de ações para melhorias futuras**

- Implementar técnicas de balanceamento de dados, como oversampling (SMOTE) ou undersampling, para equilibrar as classes no conjunto de dados.
- Coletar e incluir variáveis adicionais no conjunto de dados, como características do solo (pH, nutrientes) e tipo de cultura.
- Implementar técnicas de validação cruzada, como K-Fold Cross Validation, para garantir a robustez do modelo.
- Utilizar técnicas de interpretabilidade de modelos, como SHAP, para fornecer explicações detalhadas sobre as decisões

# <a name="c6"></a>6. Referências

- [Documentação Oficial do Scikit-learn](https://scikit-learn.org/stable/index.html)

- https://imbalanced-learn.org/stable/

- https://imbalanced-learn.org/stable/

# <a name="c7"></a>Anexos

