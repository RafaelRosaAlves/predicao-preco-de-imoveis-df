#  Predição de Preços de Imóveis no Distrito Federal (End-to-End)

Este projeto apresenta uma solução completa de **Data Science** aplicada ao mercado imobiliário. O pipeline vai desde a coleta automática de dados (Web Scraping) até a construção de um modelo de Machine Learning para precificação de imóveis.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/RafaelRosaAlves/predicao-preco-de-imoveis-df/blob/main/scrapping_dfimoveis_final.ipynb)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Selenium](https://img.shields.io/badge/Web%20Scraping-Selenium-green)
![Scikit-Learn](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange)

##  Objetivo

O objetivo principal é criar um modelo preditivo capaz de estimar o preço de venda de um imóvel no Distrito Federal com base em suas características físicas e localização, auxiliando na avaliação de mercado e tomada de decisão.

##  Arquitetura do Projeto

O projeto foi estruturado em 4 etapas principais:

1.  **Web Scraping (Coleta):**
    * Utilização do **Selenium** e **BeautifulSoup** para navegar dinamicamente no portal *DF Imóveis*.
    * Extração robusta de dados percorrendo múltiplas páginas de resultados.
    * Captura de: `Preço`, `Localização (Bairro)`, `Área (m²)` e `Número de Quartos`.

2.  **Pré-processamento e Limpeza:**
    * Tratamento de strings com **RegEx** (remoção de símbolos de moeda, formatação numérica).
    * Conversão de tipos de dados.
    * *One-Hot Encoding*: Transformação da variável categórica `Bairro` em variáveis numéricas para leitura do modelo.

3.  **Análise Exploratória (EDA):**
    * Estudo de correlação entre variáveis (Heatmap).
    * Distribuição de preços por bairro (Boxplot).
    * Relação entre Área vs. Preço (Scatterplot).

4.  **Machine Learning (Modelagem):**
    * Algoritmo: **Regressão Linear Múltipla**.
    * Separação de dados: Treino (80%) e Teste (20%).
    * Métricas de Avaliação: *MSE (Mean Squared Error)* e *R² Score*.

##  Tecnologias e Bibliotecas

* **Coleta:** `Selenium`, `BeautifulSoup`, `Webdriver Manager`
* **Manipulação:** `Pandas`, `NumPy`
* **Visualização:** `Matplotlib`, `Seaborn`
* **Machine Learning:** `Scikit-Learn` (LinearRegression, train_test_split, metrics)

##  Resultados e Visualizações

O notebook gera visualizações estratégicas para entender o mercado:

* **Matriz de Correlação:** Para entender quais fatores mais impactam no preço.
* **Boxplot por Bairro:** Identifica a variação de preço e *outliers* em diferentes regiões do DF.
* **Regressão Linear:** Gráfico comparativo entre os valores reais vs. valores preditos pelo modelo.

> *Exemplo de insight:* O modelo identifica que a variável `Área` possui forte correlação positiva com o `Preço`, mas a localização (`Bairro`) atua como um multiplicador determinante no valor final.

##  Como Executar

A maneira mais fácil de executar este projeto (devido às dependências do Selenium e Chrome Driver) é via Google Colab:

1.  Clique no botão **"Open in Colab"** no topo deste arquivo.
2.  No menu do Colab, vá em *Runtime* > *Run all* (ou *Executar tudo*).
    * *Nota: O script já contém as instruções para instalar o Chrome e o ChromeDriver no ambiente Linux do Colab.*

### Execução Local (Opcional)

Para rodar em sua máquina, você precisará configurar o WebDriver localmente:
1.  Instale as dependências:
    ```bash
    pip install pandas selenium beautifulsoup4 matplotlib seaborn scikit-learn
    ```
2.  Garanta que você tenha o Google Chrome instalado e o [ChromeDriver](https://chromedriver.chromium.org/downloads) compatível com sua versão no PATH do sistema.

---
*Desenvolvido por [SEU NOME]. Sinta-se à vontade para contribuir ou entrar em contato!*
