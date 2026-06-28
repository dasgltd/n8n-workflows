# Open Source n8n Workflows

Esta pasta contém exemplos de workflows abertos e úteis que complementam a skill **[n8n-workflow-updater](https://github.com/dasgltd/llm-skills/tree/main/skills/n8n-workflow-updater)** e ajudam a manter sua infraestrutura de automação mais profissional e resiliente.

## 1. Tratamento de Erros Global (`ErrorBot.json`)
Um fluxo projetado para atuar como o "Workflow de Erro" mestre da sua instância do n8n. Quando qualquer outro fluxo da sua conta falhar, ele chama este bot invisível passando os detalhes do erro (ID da execução, nome do fluxo quebrado, mensagem de erro), e este bot notifica você imediatamente.

> **Nota sobre Notificações:** Este arquivo `ErrorBot.json` usa um nó do **Telegram** como modelo/padrão para o envio da mensagem. No entanto, sinta-se totalmente livre para apagar o nó do Telegram e substituí-lo pelo canal que for melhor para você (Slack, Microsoft Teams, Discord, Email, etc). A lógica principal de formatação do erro continuará funcionando perfeitamente!

### Como instalar:
1. Crie um novo workflow vazio no n8n.
2. Importe o conteúdo do arquivo `ErrorBot.json`.
3. Configure suas credenciais no nó de notificação (Telegram, Slack, Discord, Email, etc.).
4. Salve e **Ative** o workflow.
5. Pegue o ID de texto deste workflow na barra de endereços (ex: `v08hZdac5oFON8nz`) e substitua a variável `errorWorkflow` no arquivo `SKILL.md` caso queira que a IA vincule os erros automaticamente.

---

## 2. GitHub Backup (`GitHubBackup.json`)
Um fluxo autônomo que realiza um backup periódico e automático de **todos** os seus workflows do n8n (arquivos JSON) direto para um repositório no GitHub. 

### Como instalar:
1. Importe o `GitHubBackup.json` para o seu n8n.
2. Crie uma credencial do GitHub no n8n fornecendo o seu Personal Access Token (PAT).
   > **🛡️ Dica de Segurança (Best Practice):**
   > Não use um token clássico com acesso total. No GitHub, crie um **"Fine-grained personal access token"**.
   > - Em **Repository access**, marque `Only select repositories` e escolha **apenas** o repositório específico de backup.
   > - Em **Permissions**, conceda apenas `Contents: Read and write` (a permissão de *Metadata: Read-only* é marcada automaticamente).
   > - Assim, mesmo que o token vaze, ele só terá acesso a essa pasta de backups e a mais nenhum repositório seu!
3. Altere o nó do GitHub para apontar para o nome do seu repositório de backup (ex: `SeuUsuario/n8n-backups`).
4. (Opcional) Ajuste a frequência de backup no nó *Schedule Trigger* (ex: para rodar de hora em hora ou apenas de madrugada).
5. Salve e **Ative** o workflow! Assim, você passa a ter controle de versão e histórico visual (commits) de toda a sua infraestrutura no-code.
