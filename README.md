# MkDocs Template for GitHub Pages

This repository provides a template for building and deploying a MkDocs site to GitHub Pages using GitHub Actions. It leverages the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme for a modern, responsive design.

## Features

- **Simple Documentation Setup:** Get started quickly with a basic MkDocs configuration.
- **Automated Deployment:** A GitHub Actions workflow automatically builds and deploys your documentation to the `gh-pages` branch on every push to `main`.
- **Custom Deploy Token:** Uses a custom Personal Access Token (PAT) via the `MKDOCS_DEPLOY_TOKEN` secret to handle repository permissions.

## Project Structure

```
mkdocs-template/
├── docs/
│   └── index.md         # Your main documentation file
├── mkdocs.yml           # MkDocs configuration file
└── .github/
    └── workflows/
         └── deploy.yml  # GitHub Actions workflow for deployment
```

## Getting Started

### 1. Fork or Clone This Repository

Clone the repository to your local machine:

```bash
git clone https://github.com/CagriCatik/mkdocs-template.git
```

### 2. Create a Personal Access Token

Since the default GitHub token might not have enough permissions for pushing to the repository, create a [Personal Access Token (PAT)](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token) with the `repo` scope.

### 3. Add the Deploy Token to Your Repository Secrets

1. Navigate to your repository on GitHub.
2. Go to **Settings** > **Secrets and variables** > **Actions**.
3. Create a new repository secret named `MKDOCS_DEPLOY_TOKEN` and paste your PAT.

### 4. Configure Branch Protection (if needed)

If you have branch protection enabled on the `gh-pages` branch, ensure that pushes from the GitHub Actions bot (using your PAT) are allowed.

### 5. Push Changes

Commit your changes and push them to the `main` branch. This will trigger the GitHub Actions workflow to build and deploy your site to GitHub Pages.

## Customizing Your Documentation

- **Update `docs/index.md`:** Edit this file to modify your site's homepage.
- **Modify `mkdocs.yml`:** Change the site name, navigation, theme options, and more as needed.
- **Add More Pages:** Create additional Markdown files under the `docs` directory and update the navigation in `mkdocs.yml` accordingly.

## GitHub Actions Workflow

The deployment workflow is defined in `.github/workflows/deploy.yml`:

- **Checkout with Deploy Token:** Uses the `MKDOCS_DEPLOY_TOKEN` to ensure proper permissions.
- **Install Dependencies:** Installs MkDocs and the Material theme.
- **Deploy:** Runs `mkdocs gh-deploy --force` to build and push your site to the `gh-pages` branch.

## Contributing

Feel free to submit issues or pull requests for improvements and bug fixes. Contributions are welcome!

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgements

- [MkDocs](https://www.mkdocs.org/)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
- [GitHub Actions](https://github.com/features/actions)
