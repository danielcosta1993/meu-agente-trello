# meu-agente-trello
Agente inteligente desenvolvido em Python para automação de fluxos de trabalho e gerenciamento de tarefas integrado à API do Trello. Projeto do desafio da DIO.

# 🤖 Agente Inteligente de Organização de Tarefas (Trello + Python ADK)

Este repositório apresenta o desenvolvimento de um agente autônomo baseado em Inteligência Artificial, projetado para gerenciar e automatizar fluxos de trabalho diretamente em quadros do Trello. O projeto foi construído utilizando o **Agent Development Kit (ADK)** da Google e o modelo **Gemini 2.5 Flash** como desafio final na plataforma DIO.

---

## 🎯 Objetivo do Agente

O `root_agent` atua como um assistente de produtividade pessoal. Ao iniciar, ele interage com o usuário perguntando as demandas pendentes, coleta o contexto de data/hora atual e cria, lista ou move cartões dentro de um quadro específico no Trello de forma totalmente autônoma.

---

## 🚀 Funcionalidades Implementadas

O agente possui acesso a ferramentas (*tools*) em Python que o capacitam a realizar as seguintes ações:

*   **`get_temporal_context`**: Captura a data e a hora exata da interação. Ajustado estruturalmente para suportar fuso horário local e evitar quebras de cronograma.
*   **`adicionar_tarefa`**: Cria novos cartões no Trello com título, descrição detalhada e data de entrega dentro da lista "A Fazer" ou "To Do".
*   **`listar_tarefas`**: Consulta e filtra os cartões do quadro com base no status atual (*A Fazer*, *Em Andamento*, *Concluído* ou *Todas*).
*   **`mudar_status_tarefa`**: Automatiza a movimentação física de cartões entre as colunas do quadro à medida que o usuário reporta o progresso.

---

## 🛠️ Tecnologias Utilizadas

*   **Linguagem:** Python 3.9+
*   **Orquestração de Agentes:** Google Agent Development Kit (ADK)
*   **Modelo de Linguagem (LLM):** Google Gemini 2.5 Flash
*   **Integração de API:** `py-trello` (TrelloClient)
*   **Gerenciamento de Ambiente:** `python-dotenv` e `zoneinfo`

---

## 🔧 Configuração do Ambiente

### 1. Estrutura do Quadro no Trello
Para o correto funcionamento das ferramentas, certifique-se de possuir um quadro público ou privado no Trello com as seguintes especificações:
*   **Nome do Quadro:** `DIO`
*   **Nomes das Listas (Colunas):** `A FAZER` (ou `TO DO`), `EM ANDAMENTO` e `CONCLUÍDO`.

### 2. Variáveis de Ambiente (`.env`)
Crie um arquivo chamado `.env` na raiz do seu projeto contendo as suas chaves de acesso:

```env
GEMINI_API_KEY=sua_chave_do_gemini_aqui
TRELLO_API_KEY=sua_api_key_do_trello_aqui
TRELLO_API_SECRET=seu_api_secret_do_trello_aqui
TRELLO_TOKEN=seu_token_autorizado_do_trello_aqui
```

### 3. Instalação das Dependências
Instale as bibliotecas necessárias executando o comando abaixo no seu terminal:

```bash
pip install py-trello python-dotenv google-adk
```

---

## 🔄 Como Executar o Projeto

1. Certifique-se de descomentar a função `main()` e o bloco de execução assíncrona ao final do arquivo `agent.py`.
2. Execute o script principal:

```bash
python agent.py
```

3. O agente iniciará a execução via terminal, saudando você com a data atualizada e solicitando a lista de tarefas do seu dia.

---
🔬 *Projeto desenvolvido como critério de avaliação no Bootcamp de IA e Agentes Autônomos da Digital Innovation One (DIO).*
