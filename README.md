# **Check Point 3 - DSS - Análise de dados com AI e ML Scikit-learn**
Anny Dias - RM: 98295

Henrique Lima - RM: 551528

David Denunci - RM: 98603

# **Análise de Aplicativos da Google Play Store**
**1. Introdução**

Este projeto tem como objetivo investigar os fatores que influenciam a popularidade e a avaliação de aplicativos na Google Play Store. Utilizando dados do Google Play, analisamos como variáveis como o número de instalações, categoria, tamanho e preço impactam a aceitação dos usuários. A seguir estão as principais perguntas de pesquisa que orientam esta análise:

**Perguntas de Pesquisa**
*   Qual é a relação entre Category, Installs, e Rating?
* Como o Price e o Type do aplicativo impactam sua popularidade (Installs) e aceitação (Rating)?
* Existem padrões distintos entre categorias que se destacam em Rating e Installs?
* Quais fatores mais influenciam o rating de um aplicativo?
* Existe uma relação entre a categoria de um aplicativo e o número de instalações?
* Qual é o impacto do preço (gratuito ou pago) na popularidade e na avaliação do aplicativo?
* Como o tamanho do aplicativo afeta sua popularidade e avaliação?
* Aplicativos de quais categorias tendem a ter as melhores e piores avaliações?
* Existe uma correlação entre a quantidade de avaliações (Reviews) e a nota média do aplicativo (Rating)?
* Qual é o impacto do tamanho de instalação (Size) nos ratings dos aplicativos?

**2. Metodologia**

**2.1 Obtenção dos Dados**

O dataset foi obtido através de uma amostra de aplicativos da Google Play Store, contendo informações como App, Category, Rating, Reviews, Size, Installs, Type, Price e Genres. A análise foi realizada em Python com as bibliotecas Pandas, Seaborn e Matplotlib.

**2.2 Limpeza e Preparação dos Dados**

Para garantir uma análise precisa, seguimos as etapas abaixo:

* **Remoção de Outliers em Ratings:** Filtramos para manter valores de Rating dentro do intervalo de 1 a 5.
* **Tratamento de Valores Ausentes:**
  * **Rating:** Valores ausentes foram preenchidos com a média dos ratings.
  * **Reviews, Installs, e Price:** Convertidos para valores numéricos, após limpeza de símbolos (ex: +, , e $).
  * **Size:** Convertido para uma unidade única (KB) e valores como "Varies with device" foram substituídos por NaN e preenchidos com a média do Size.

Essas transformações foram realizadas para padronizar o dataset e permitir análises de correlação e regressão com variáveis numéricas.

**3. Resultados**

Após a limpeza dos dados, realizamos uma análise exploratória para identificar padrões e relações entre as variáveis. Abaixo estão os gráficos que ilustram as principais descobertas:

**3.1 Distribuição de Ratings**


A maioria dos aplicativos apresenta uma avaliação entre 4.0 e 4.5, indicando uma satisfação média-alta entre os usuários. O viés positivo nas avaliações sugere que a maioria dos aplicativos atende às expectativas do público.

**3.2 Distribuição de Installs (Escala Logarítmica)**


A distribuição de instalações (em escala logarítmica) mostra que poucos aplicativos ultrapassam a marca de milhões de instalações, enquanto muitos permanecem abaixo dos 100 mil downloads. Este é um padrão comum, onde um pequeno número de aplicativos domina o mercado.

**3.3 Relação entre Rating e Installs**


Este gráfico mostra que aplicativos com um número muito alto de instalações tendem a manter uma avaliação entre 4.0 e 4.5. No entanto, essa relação não é forte, sugerindo que a popularidade de um aplicativo (medida por instalações) não é um indicador definitivo de sua avaliação.

**3.4 Distribuição de Ratings por Categoria**


Categorias como "BOOKS_AND_REFERENCE" e "EDUCATION" possuem avaliações relativamente altas, enquanto outras, como "FAMILY" e "GAME", mostram uma maior variabilidade nas avaliações. Essa análise por categoria revela onde as expectativas dos usuários são melhor atendidas.

**3.5 Modelagem Preditiva**

Para entender os fatores que afetam as avaliações, aplicamos uma Regressão Linear com Installs, Price, Size e Category como variáveis independentes para prever o Rating.

* **Mean Squared Error (MSE): 0.32**
* **Coeficiente de Determinação (R²): 0.15**

Estes resultados mostram que o modelo tem um desempenho limitado para prever a avaliação de um aplicativo. O valor baixo de R² indica que os fatores utilizados no modelo explicam apenas 15% da variabilidade nos Ratings.

**4. Conclusões**

A análise revelou que, embora existam alguns padrões entre categorias e características dos aplicativos, muitos fatores que afetam a avaliação dos usuários não estão totalmente capturados neste dataset. Fatores externos, como a qualidade da experiência do usuário, as atualizações e a comunicação do desenvolvedor, podem influenciar significativamente a aceitação do aplicativo.
