---
title: Getting started
---

To create your own documentation site using GitHub Profile Kit, follow these steps:

- Visit the [GitHub Profile Kit repository](https://github.com/HYP3R00T/github-profile-kit).
- Click on the “Use this template” button.
- Follow the prompts to create a new repository using this template.
- Make sure the name of repository is exactly the same as your username.

## Local Setup

The project is powered by Python. To manage the project we are using [uv](https://docs.astral.sh/uv/). Check the official documentation regarding system specific installation.

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Create a virtual environment using `uv`.

```bash
uv venv
```

Activate the virtual environment.

```bash
 source ./.venv/bin/activate # This command might vary depending on your OS and shell
```

Install all the packages in the virtual environment.

```bash
uv sync
```

## Run the Script

Of course, you need to make changes as per your requirements but once done you can run the script.

```bash
uv run python src/main.py
```

---

## References

- [Managing your profile README](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme)
- [uv](https://docs.astral.sh/uv/)