---
title: Secret Management
---

Managing tokens and other secrets securely is crucial in both local development and continuous integration pipelines like GitHub Actions. Some blocks might need you to use API tokens to verify credentials and fetch information.

For instance, you want to list the lastest videos of your channel, you need to add the API Token to the environment.

## Local Development

We use `.env` file to manage environment-specific configurations. For security reasons, we have added it to `.gitignore` file. For you we have shared a `sample.env` file. You can create a copy of it.

```bash
cp sample.env .env
```

In this environment file, you can add tokens and other secrets. This will let you run the script locally without any error. Refer to indivisual blocks to learn more about how to generate tokens and store them.

## GitHub Actions Pipeline

GitHub allows you to store secrets at the repository level. To add a secret

  1. Navigate to your repository on GitHub.
  2. Click on the "Settings" tab.
  3. In the "Security" section of the sidebar, select "Secrets and variables," then click "Actions."
  4. Click the "Secrets" tab.
  5. Click "New repository secret."
  6. Enter a name and value for your secret, then click "Add secret."
