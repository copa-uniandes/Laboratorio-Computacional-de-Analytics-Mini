# Laboratorio-Computacional-de-Analytics

[![Deploy-to-web](https://github.com/copa-uniandes/Laboratorio-Computacional-de-Analytics/actions/workflows/main.yml/badge.svg)](https://github.com/copa-uniandes/Laboratorio-Computacional-de-Analytics/actions/workflows/main.yml)

## Downstream applications

__Partial mirror__:

https://github.com/copa-uniandes/Laboratorio-Computacional-de-Analytics-Mini/

__Static website and MyBinder__:

https://github.com/copa-uniandes/PAD-web-tutorials

## Troubleshooting the Workflow:
> Error: fatal: could not read Username for 'https://github.com': terminal prompts disabled

> Error: The process '/usr/bin/git' failed with exit code 128

This is because secret codes are not updated. You should generate new secrets and updating the information in LCA repo. Follow these steps to accomplish that:

1. Generate a Personal Access Token:

- Go to your GitHub account settings: GitHub Account Settings.
- Navigate to "Developer settings" -> "Personal access tokens" or use this link: GitHub Personal Access Tokens.
- Click on "Generate new token" to create a new access token.
- Select the appropriate scopes (permissions) for your token. For this workflow, you'll need to select the "repo" scope to access private repositories.
- Click "Generate token" and copy the generated token. Remember to keep the token confidential and avoid sharing it publicly.

2. Add the Personal Access Token to GitHub Secrets:

- In your GitHub repository, go to "Settings" from the top menu.
- Click on "Secrets" in the left sidebar.
- Click on "New repository secret" to add a new secret.
- Name the secret, for example, ACCESS_TOKEN.
- Paste the copied personal access token as the value.
- Click "Add secret" to save the token securely as a GitHub secret.

3. Update the Workflow:

- In your workflow file (e.g., .github/workflows/main.yml), replace ${{ secrets.ACCESS_TOKEN }} with the name of the secret you created in step 2, i.e., ACCESS_TOKEN.
