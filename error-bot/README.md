# Tratamento de Erros Global (Error Bot)

Um fluxo projetado para atuar como o "Workflow de Erro" mestre da sua instância do n8n. Quando qualquer outro fluxo da sua conta falhar, ele chama este bot invisível passando os detalhes do erro (ID da execução, nome do fluxo quebrado, mensagem de erro), e este bot notifica você imediatamente.

> **Nota sobre Notificações:** Este arquivo `ErrorBot.json` usa um nó do **Telegram** como modelo/padrão para o envio da mensagem. No entanto, sinta-se totalmente livre para apagar o nó do Telegram e substituí-lo pelo canal que for melhor para você (Slack, Microsoft Teams, Discord, Email, etc). A lógica principal de formatação do erro continuará funcionando perfeitamente!

## Como instalar:
1. Crie um novo workflow vazio no n8n.
2. Importe o conteúdo do arquivo `ErrorBot.json`.
3. Configure suas credenciais no nó de notificação (Telegram, Slack, Discord, Email, etc.).
4. Salve e **Ative** o workflow.
5. Pegue o ID de texto deste workflow na barra de endereços (ex: `v08hZdac5oFON8nz`) e substitua a variável `errorWorkflow` no arquivo `SKILL.md` da skill do n8n caso queira que a IA vincule os erros automaticamente.
