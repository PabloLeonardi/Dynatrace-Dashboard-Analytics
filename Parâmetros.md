# 🛠️ Configuração de Parâmetros no Power BI

Para que o dashboard de monitoramento funcione corretamente e se conecte à API do **Dynatrace**, é necessário configurar quatro parâmetros globais. Esses parâmetros garantem que as consultas sejam dinâmicas e seguras.

## 📍 Passo a Passo para Criação

1. No Power BI Desktop, vá até a guia **Modelagem** (Modeling).
2. Clique no botão **Gerenciar Parâmetros** e selecione **Novo Parâmetro**.
3. Crie os quatro parâmetros abaixo conforme as especificações:

---

### 1. Dynatrace_URL
Este parâmetro define o endpoint base da sua instância.
* **Tipo:** `Texto`
* **Valor Sugerido:** `https://SUA_URL.live.dynatrace.com/`
* **⚠️ Atenção:** Certifique-se de incluir a barra `/` ao final da URL.

### 2. Dynatrace_Token
Token de autenticação para acesso aos dados.
* **Tipo:** `Texto`
* **Valor Sugerido:** `dt0c01.xxxxxxxxxxxxxx`
* **💡 Nota:** O token deve possuir permissões de **Read (Leitura)** para todas as entidades e problemas (`v2 API scopes`) para garantir o funcionamento total das consultas.

### 3. Page_Size
Define a volumetria de registros por página na requisição da API.
* **Tipo:** `Qualquer` (ou Número Inteiro)
* **Valor Sugerido:** `500`
* **Por que usar?** Controla a paginação para evitar timeouts em ambientes com alta volumetria de alertas.

### 4. Data_Inicio
Define o marco zero da coleta de dados histórica.
* **Tipo:** `Texto`
* **Valor Sugerido:** `01/01/2025 00:00:00`
* **Formato:** Use o padrão `DD/MM/AAAA HH:MM:SS`.

---

> [!IMPORTANT]
> **Dica de Segurança:** Nunca suba o seu arquivo `.pbix` para o GitHub com o seu **Token Real** preenchido no "Valor Atual". Limpe os parâmetros ou use valores fictícios antes de realizar o commit para proteger o acesso ao seu ambiente Dynatrace.
