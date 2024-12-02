
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

*A FarmTech Solutions atua no crescente segmento da agricultura de precisão, utilizando a inteligência artificial para otimizar processos agrícolas e aumentar a produtividade. Nossa solução se concentra em desenvolver ferramentas e plataformas que utilizam dados de sensores, imagens de satélite e outras fontes para fornecer insights valiosos aos agricultores. Através da análise desses dados, nossos sistemas podem identificar padrões, prever resultados e recomendar ações personalizadas, como a aplicação precisa de fertilizantes e a otimização da irrigação. Essa abordagem permite que os agricultores maximizem a eficiência de seus recursos, reduzam custos e contribuam para a sustentabilidade do agronegócio. Nosso foco inicial é o mercado brasileiro, onde a agricultura desempenha um papel fundamental na economia, mas vislumbramos expandir nossas operações para outros países da América Latina e, futuramente, para o mercado global.*

### 1.1.2. Descrição da Solução Desenvolvida

*Utilizando sensores IoT e algoritmos de machine learning, a FarmTech Solutions desenvolveu uma plataforma de agricultura de precisão que transforma dados em insights acionáveis. Através de sensores instalados no campo, coletamos dados em tempo real sobre a umidade do solo e outros parâmetros relevantes para a cultura (fósforo (P) e potássio (K)). Com base nessas informações, nosso sistema ajusta automaticamente a frequência e a duração da irrigação, garantindo que as plantas recebam a quantidade exata de água necessária para um desenvolvimento saudável e otimizando o uso desse recurso essencial.*

# <a name="c2"></a>2. Visão Geral do Projeto

## 2.1. Objetivos do Projeto

*Este projeto tem como objetivo desenvolver uma solução tecnológica que automatiza o processo de irrigação, tornando-o mais eficiente e preciso. Utilizando sensores e um microcontrolador, o sistema monitora continuamente as condições do solo e aciona a bomba d'água de forma autônoma, adaptando-se às necessidades específicas de cada plantação.*

## 2.2. Público-Alvo

*Agricultores que buscam uma solução tecnológica para automatizar a irrigação e tomar decisões baseada em dados para gerenciar suas plantações.*

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

*As bibliotecas necessárias foram importadas, incluindo ferramentas para manipulação de dados (pandas), visualização (seaborn e matplotlib), criação de pipelines (sklearn.pipeline), pré-processamento (sklearn.preprocessing), validação cruzada (sklearn.model_selection), classificação (sklearn.ensemble) e serialização de modelos (joblib).*

## 3.2. Modelagem e Algoritmos

*Descreva os modelos e algoritmos de IA utilizados no projeto. Explique por que esses modelos foram escolhidos e como foram implementados.*

*O principal modelo de IA utilizado neste projeto foi o RandomForestClassifier, que é um algoritmo de aprendizado supervisionado usado para classificação. Ele consiste em um conjunto de árvores de decisão e opera construindo múltiplas árvores durante o treinamento e gerando a classe que é o modo das classes (classificação) ou a média das previsões (regressão) das árvores individuais.*

*A implementação do RandomForestClassifier foi realizada através de um pipeline de pré-processamento e classificação*

O uso do RandomForestClassifier neste projeto se mostrou adequado devido à sua robustez, precisão, resistência ao overfitting e capacidade de avaliar a importância das variáveis. A implementação através do pipeline de pré-processamento e classificação com a biblioteca scikit-learn facilitou o desenvolvimento e a manutenção do modelo, garantindo um fluxo de trabalho eficiente e eficaz para a previsão da necessidade de irrigação automática.

## 3.3. Treinamento e Teste

*Descreva o processo de treinamento e teste dos modelos de IA. Inclua informações sobre os conjuntos de dados utilizados, métricas de avaliação e resultados obtidos.*

# <a name="c4"></a>4. Resultados e Avaliações

## 4.1. Análise dos Resultados

*Analise os resultados obtidos com os modelos de IA. Compare os resultados esperados com os resultados reais e discuta as possíveis razões para as diferenças.*

## 4.2. Feedback dos Usuários

*Inclua feedback recebido de usuários finais durante o processo de avaliação do projeto.*

# <a name="c5"></a>5. Conclusões e Trabalhos Futuros

*Descreva de que formas a solução desenvolvida atingiu os objetivos do projeto. Indique pontos fortes e pontos a melhorar. Relacione os pontos de melhorias evidenciados e elabore um plano de ações para serem implementadas no futuro.*

# <a name="c6"></a>6. Referências

_Incluir as principais referências de seu projeto, para que outros possam consultar caso tenham interesse em aprofundar._

# <a name="c7"></a>Anexos

*Inclua aqui quaisquer complementos para seu projeto, como diagramas, imagens, tabelas etc. Organize em sub-tópicos utilizando headings menores (use ## ou ### para isso).*
