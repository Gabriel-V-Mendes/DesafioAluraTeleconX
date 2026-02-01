# DesafioAluraTeleconX

# 📡 Análise de Churn (Evasão) - Telecom X

![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Libs](https://img.shields.io/badge/Libs-Pandas%20|%20Seaborn%20|%20Plotly-orange)

## 📋 Descrição do Projeto

Este projeto visa analisar o **Churn (Taxa de Cancelamento)** da empresa Telecom X. O objetivo principal foi identificar padrões de comportamento dos clientes e entender quais fatores levam à evasão, fornecendo insights estratégicos para a tomada de decisão.

O desafio abrangeu desde a coleta de dados brutos (simulando uma API) até a análise exploratória avançada, passando por etapas rigorosas de limpeza e engenharia de atributos.

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python
* **Manipulação de Dados:** Pandas, NumPy, JSON
* **Visualização:** Matplotlib, Seaborn, Plotly

## ⚙️ Etapas do Desenvolvimento

### 1. Extração e Transformação (ETL)
Os dados originais foram carregados a partir de um arquivo JSON complexo, contendo objetos aninhados (`customer`, `phone`, `internet`, `account`).
* Utilizei `pd.json_normalize` para "achatar" a estrutura e transformar em uma tabela única.
* Renomeei as colunas programaticamente para remover prefixos técnicos e facilitar o acesso.

### 2. Limpeza de Dados
Fase crítica para garantir a integridade da análise:
* **Conversão de Tipos:** A coluna `Charges.Total` continha strings vazias (`" "`) que foram tratadas e convertidas para formato numérico (`float`).
* **Remoção de Inconsistências:** Registros sem rótulo na variável alvo (`Churn`) foram removidos do dataset.
* **Tradução:** Colunas e valores categóricos foram traduzidos para o Português (ex: 'Yes' -> 'Sim'), facilitando a interpretação por stakeholders locais.
* **Feature Engineering:** Criação da variável `Contas_Diarias` (divisão da fatura mensal por 30) para uma análise mais granular do impacto financeiro no bolso do cliente.

### 3. Análise Exploratória e Insights
Através de gráficos estatísticos e análises de correlação, identificamos os seguintes padrões:

* 📉 **Contratos Mensais:** Representam a maior fatia de cancelamentos, indicando baixa fidelidade neste modelo.
* 💸 **Método de Pagamento:** Clientes que pagam via **Cheque Eletrônico** tendem a sair mais do que aqueles com cartão de crédito ou transferência.
* 👴 **Fidelidade:** A taxa de churn despenca após os primeiros meses. Clientes novos são os mais vulneráveis.
* 🌐 **Fibra Óptica:** Clientes com este serviço cancelam significativamente mais do que os usuários de DSL, sugerindo possível insatisfação com o preço ou a qualidade técnica específica deste serviço.

## 📊 Visualizações

O notebook inclui diversas visualizações para sustentar as conclusões:
* **Pie Charts:** Para visualizar a proporção geral de evasão.
* **Boxplots:** Para analisar a distribuição de valores pagos entre clientes que saíram e que ficaram.
* **Heatmap de Correlação:** Para identificar matematicamente quais variáveis (como *Tempo de Contrato* e *Valor da Fatura*) estão mais fortemente ligadas à decisão de cancelar.

## ✒️ Autor

**Gabriel V Mendes**

* [LinkedIn](https://www.linkedin.com/in/gabrielvmendes-dev/)
---
*Este projeto foi desenvolvido como parte de um desafio prático de Data Science do programa ONE oracle next education em parceria com a ALURA.*
