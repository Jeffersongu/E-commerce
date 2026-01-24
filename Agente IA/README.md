## Agente de IA com N8N

O objetivo é criar um Agente de IA usando n8n, permitindo que usuários conversem com seu banco de dados de forma natural através do Telegram. O agente de IA funcionará no Telegram que consulta o banco Supabase usando linguagem natural.

<p align="center">
<img src="https://github.com/user-attachments/assets/701585f2-6c6b-4906-96c4-ead99338c432" width="600" alt="image">
</p>

---

Agentes de IA são sistemas que combinam modelos de linguagem (como GPT) com ferramentas externas (Tools) para realizar tarefas complexas de forma autônoma.

Agentes de IA permitem:

- Conversar naturalmente - Usuários fazem perguntas em linguagem natural
- Acessar dados reais - Consultar bancos de dados, APIs, planilhas
- Memorizar contexto - Lembrar informações de conversas anteriores
- Aplicar guardrails - Limitar o comportamento do agente
- Executar ações - Fazer queries, cálculos, análises automaticamente


## Fluxo de Dados com Agente de IA

O diagrama abaixo mostra como o Agente de IA funciona:

<img width="721" height="847" alt="image" src="https://github.com/user-attachments/assets/00eeae47-7a42-40d8-ba13-300cb4e489d5" />

---



## Etapa 1: Agente de E-commerce

Objetivo: Criar um agente especializado em e-commerce
- System Message: Instruções que definem o comportamento do agente
- Guardrails: Limites que previnem respostas indesejadas
- Prompt Engineering: Como escrever instruções eficazes


---

## Etapa 2: Memória em Agentes de IA

Objetivo: Mostrar como o agente memoriza informações da conversa.
- Como configurar memória no n8n

---


## Etapa 3: Consultando Tabela com Tool (Supabase)

Objetivo: Fazer o agente consultar o Supabase usando Tools.
- Tools: Ferramentas externas que o agente pode usar
- Function Calling: Como o agente decide usar uma Tool
- Schema de Tool: Como descrever uma Tool para o agente
- PostgreSQL Tool: Tool específica para consultar banco de dados



