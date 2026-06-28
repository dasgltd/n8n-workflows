# GitHub Backup

Um fluxo autônomo que realiza um backup periódico e automático de **todos** os seus workflows do n8n (arquivos JSON) direto para um repositório no GitHub. 

## Como instalar:
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
