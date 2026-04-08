# 📈 Dynatrace Analytics: Observabilidade e Inteligência Operacional

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Dynatrace](https://img.shields.io/badge/Dynatrace-732777?style=for-the-badge&logo=dynatrace&logoColor=white)
![Data Analytics](https://img.shields.io/badge/Data_Analytics-Blue?style=for-the-badge)
![SRE](https://img.shields.io/badge/SRE-Operational_Excellence-green?style=for-the-badge)

## 🎯 Objetivo do Projeto
Este projeto consiste em um ecossistema de análise de dados extraídos via API do **Dynatrace**, focado na redução de incidentes e otimização do tempo de resposta (MTTR). Através de consultas complexas e modelagem de dados avançada, a solução entrega uma visão clara sobre a saúde do ambiente e a eficiência dos processos de TI.

O objetivo principal é a **identificação proativa de ofensores**, permitindo que a equipe de operações deixe de apenas "apagar incêndios" e passe a atuar na causa raiz dos problemas estruturais.

---

## 🖥️ Arquitetura dos Dashboards

O projeto é dividido em duas camadas estratégicas:

### 1. Dashboard Operacional
Focado na análise técnica e imediata dos incidentes dentro de um período determinado. É a ferramenta principal para a **Gestão de Problemas**.

* **Principais KPIs:**
    * **Root Cause Recorrente:** Identifica a entidade (Host, Service, Process) que mais origina falhas, direcionando o foco da engenharia.
    * **Problema mais Recorrente:** Mapeia o sintoma (ex: CPU Saturation, Failure rate increase) com maior frequência.
    * **Top 5 RootCause:** Mostra as 5 RootCause mais recorrentes dentro do periodo selecionado

![Dashboard Operacional](/images/Dashboard_operacional.png)


### 2. Dashboard Overview (Visão Executiva)
Focado na análise histórica e tendência mensal. Serve para validar se as ações tomadas no nível operacional estão gerando resultados reais no longo prazo.

* **Métricas de Desempenho:**
    * **Disponibilidade Geral por Serviço:** Monitoramento de SLAs críticos para o negócio.
    * **Downtime Acumulado:** Soma total do tempo de indisponibilidade (Severity: Availability).
    * **Análise Comparativa:** Variação percentual de Alertas e MTTR entre meses distintos para medir a eficiência da evolução do ambiente.

![Dashboard Operacional](/images/Dashboard_overview_semVariação.png)
![Dashboard Operacional](/images/Dashboard_overview_ComparandoMeses.png)

---

## 🧠 Inteligência de Dados (DAX)
Medidas desenvolvidas para tratar dados de incidentes:

* **Cálculo de Duração:** Lógica que contabiliza o tempo de incidentes fechados.
* **Média Iterativa (AVERAGEX):** Utilizada para garantir que a disponibilidade de um serviço não mascare a falha de outro, trazendo uma visão real da saúde do ecossistema.
* **Identificação de Ofensores (TOPN):** Algoritmos para isolar dinamicamente a causa raiz e o problema mais frequente.

---

## 🏗️ Modelo de Dados
A estrutura foi montada seguindo as melhores práticas de **Star Schema**, garantindo performance nas consultas:

* **Fato:** `Probl_Impacted` (Centralização de todos os eventos de incidentes).
* **Dimensões:** `Calendário`, `Entities_Base` (Hosts, Services, Applications).

![Modelo de Dados](images/modelo_dados.png)

---

## 🛠️ Tecnologias Utilizadas
* **Dynatrace API:** Extração de dados complexos de incidentes.
* **Power BI:** Modelagem, DAX Avançado e Data Viz.
* **Metodologia ITIL/SRE:** Foco em redução de ruído e melhoria contínua.

---

## 👤 Autor
**Pablo B. Leonardi**
* Analista de Operações e Planejamento
* [LinkedIn](https://www.linkedin.com/in/pablo-leonardi-198b56248/) | [GitHub](https://github.com/PabloLeonardi)
