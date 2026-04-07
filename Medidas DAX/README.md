# 📊 Documento das medidas DAX

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Dynatrace](https://img.shields.io/badge/Dynatrace-732777?style=for-the-badge&logo=dynatrace&logoColor=white)

## 🚀 Indicadores e Inteligência DAX

Abaixo, detalho as métricas personalizadas criadas para este modelo de dados, organizadas por categoria:

### 🛡️ Disponibilidade e SLA
* **Disponibilidade %**: Calcula o uptime real cruzando o tempo total do período com o tempo de indisponibilidade.
* **Disponibilidade Geral %**: Utiliza a função `AVERAGEX` para medir a saúde individual de cada entidade, evitando que um serviço isolado mascare a média do parque.
* **Tempo Total (Minutos)**: Base de cálculo dinâmica que converte a seleção do calendário em minutos totais ($Dias \times 1440$).
* **Downtime Availability**: Soma ponderada dos minutos de queda, filtrando exclusivamente incidentes de severidade crítica.

### ⚡ Performance e Resposta (MTTR)
* **MTTR (Minutos)**: Média do tempo de reparo. Essencial para medir a agilidade do suporte N2/N3.
* **Duração Minutos**: Lógica avançada que calcula o tempo de incidentes fechados e **incidentes ainda em aberto** em tempo real usando a função `NOW()`.
* **Variação MTTR %**: Compara o desempenho entre dois meses, indicando se a equipe está sendo mais rápida ou mais lenta na resolução.
* **Downtime Formatado**: Conversão de minutos brutos para o formato amigável (ex: `2h 15m`).

### 🔍 Análise de Causa Raiz (RCA)
* **RootCauseMaisRecorrente**: Identifica qual entidade (Host, DB, Processo) foi a origem da maioria das falhas.
* **ProblemMaisRecorrente**: Aponta o título do erro/sintoma mais frequente no ambiente.
* **Total de Alertas**: Contagem distinta de IDs únicos, garantindo que um incidente que afete vários serviços seja contado como um único evento de falha.

---

## 🛠️ Tecnologias Utilizadas
* **Power BI Desktop**: Modelagem e Visualização.
* **Linguagem DAX**: Cálculos iterativos e inteligência de tempo.
* **Power Query (M)**: Tratamento e limpeza dos dados de incidentes.

---

> **Desenvolvido por Pablo B. Leonardi** > *Analista de Operações e Negócios> [LinkedIn](SEU_LINK_DO_LINKEDIN_AQUI) | [GitHub](https://github.com/SEU_USUARIO_AQUI)
