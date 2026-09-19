# Dashboard Tributário - G&P Consultoria

## Visão Geral
Este projeto consiste em um dashboard interativo desenvolvido em formato de arquivo único (Single-Page Application contida no `index.html`). Ele foi criado para fornecer uma visualização clara, rápida e profissional das métricas tributárias e financeiras da empresa Garantia e Proteção, auxiliando na tomada de decisão e no acompanhamento analítico.

O arquivo foi construído focando na **desacoplagem da lógica visual em relação aos dados**, permitindo que futuras integrações (como planilhas Excel ou APIs) possam injetar dados de forma simplificada sem alterar a estrutura da interface.

## 🎯 Objetivo
O arquivo `index.html` foi criado para centralizar a análise de faturamento e impostos. No contexto tributário brasileiro, métricas como o **Faturamento Acumulado dos Últimos 12 Meses (R12)** são cruciais para o enquadramento de alíquotas (especialmente no Simples Nacional). Este dashboard automatiza a visualização dessa relação, cruzando o imposto devido com a alíquota efetiva ao longo do tempo.

## ✨ Funcionalidades
*   **Métricas de Desempenho (KPIs):** Resumo dinâmico contendo:
    *   Faturamento Mensal (Totalizado de acordo com o filtro).
    *   Faturamento Acumulado (R12) Máximo no período.
    *   Total de Impostos Devidos (Guia DAS).
    *   Alíquota Efetiva Média.
*   **Filtros Dinâmicos:** Filtros de Ano e Mês gerados automaticamente com base na fonte de dados providenciada.
*   **Visualização Gráfica Avançada:**
    *   Gráfico de barras e linhas combinadas para comparar o *Faturamento Mensal vs. Faturamento Acumulado R12*.
    *   Gráfico de eixo duplo para comparar o *Imposto Total vs. Alíquota Efetiva*.
*   **Design Responsivo:** A interface se adapta perfeitamente a diferentes tamanhos de tela (desktop, tablets e mobile).

## 🛠️ Tecnologias Utilizadas
Como o projeto foi projetado para ser leve e portátil, ele não requer processos complexos de build ou instalação de pacotes (Node.js/NPM). 

*   **HTML5 & CSS3:** Estruturação semântica e estilização utilizando variáveis CSS (Custom Properties), CSS Grid e Flexbox.
*   **JavaScript (Vanilla ES6):** Lógica de filtragem, cálculos matemáticos de array (reduce, map) e renderização do DOM.
*   **Apache ECharts (v5.5.0):** Biblioteca de renderização gráfica de alta performance utilizada via CDN.
*   **Google Fonts (Inter):** Tipografia moderna otimizada para legibilidade em dashboards.

## 🚀 Como Utilizar
Por se tratar de um arquivo "Stand-Alone" (independente), a utilização é extremamente simples:
1. Faça o download ou clone o repositório contendo o arquivo `index.html`.
2. Dê um duplo clique no arquivo `index.html` para abri-lo no seu navegador web padrão (Google Chrome, Firefox, Edge, Safari).
3. Não é necessário nenhum servidor local para visualizar o painel inicial.

## 🔄 Como Atualizar os Dados (Integração)
Atualmente, os dados são carregados de forma modular através da constante `DATA_SOURCE` localizada na tag `<script>` dentro do arquivo `index.html`. 

Para atualizar os dados com informações extraídas do seu sistema ERP ou de uma planilha Excel:
1. Abra o arquivo `index.html` em um editor de texto ou código (como VS Code ou Bloco de Notas).
2. Localize o array de objetos `DATA_SOURCE`.
3. Substitua o conteúdo do array com os novos dados em formato JSON, garantindo que as chaves coincidam (`Ano`, `Mes`, `Meses_Str`, `Fat_Mensal`, `Fat_Anual_R12`, `Imposto_Total`, `Aliq_Efetiva`).

*Exemplo da estrutura esperada:*
```json
{
  "Ano": "2024", 
  "Mes": "03", 
  "Meses_Str": "2024-03", 
  "Fat_Mensal": 60000.00, 
  "Fat_Anual_R12": 650000.00, 
  "Imposto_Total": 5800.00, 
  "Aliq_Efetiva": 0.096 
}
```

---
**Desenvolvido para G&P Consultoria**