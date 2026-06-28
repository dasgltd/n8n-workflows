# GitHub Backup

An autonomous workflow that performs a periodic, automatic backup of **all** your n8n workflows (JSON files) straight into a GitHub repository.

## How to Install:
1. Import `GitHubBackup.json` into your n8n instance.
2. Create a GitHub credential in n8n by providing your Personal Access Token (PAT).
   > **🛡️ Security Best Practice:**
   > Do not use a classic token with full access. In GitHub, create a **"Fine-grained personal access token"**.
   > - Under **Repository access**, select `Only select repositories` and pick **only** your specific backup repository.
   > - Under **Permissions**, grant only `Contents: Read and write` (the *Metadata: Read-only* permission is checked automatically).
   > - This way, even if the token leaks, it will only have access to your backup folder and no other repositories!
3. Change the GitHub node to point to your backup repository's name (e.g., `YourUsername/n8n-backups`).
4. (Optional) Adjust the backup frequency in the *Schedule Trigger* node (e.g., to run hourly or only at midnight).
5. Save and **Activate** the workflow! You now have full version control and visual history (commits) of your entire no-code infrastructure.

## Keywords
*Automated Backup, GitHub Version Control, Git, Security, Fine-Grained Personal Access Token, CI/CD, DevOps, n8n.*
