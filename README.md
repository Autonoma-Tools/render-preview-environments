# Render Preview Environments: Setup, Limitations, and How to Add E2E Testing

Companion code for the Autonoma blog post 'Render Preview Environments: Setup, Limitations, and How to Add E2E Testing'.

> Companion code for the Autonoma blog post: **[Render Preview Environments: Setup, Limitations, and How to Add E2E Testing](https://getautonoma.com/blog/render-preview-environments)**

## Requirements

A Render workspace on a paid plan (Preview Environments require a paid tier). A GitHub repo connected to Render. An Autonoma account with an API key from https://getautonoma.com. Optional: Basic Auth credentials if your previews are password-protected.

## Quickstart

```bash
git clone https://github.com/Autonoma-Tools/render-preview-environments.git
cd render-preview-environments
1) Copy render.yaml to the root of your project and commit it. 2) In Render, connect your repo and confirm Pull Request Previews are enabled on the workspace. 3) Copy .github/workflows/render-preview-e2e.yml into your repo. 4) Add these secrets to GitHub: RENDER_API_KEY, RENDER_SERVICE_ID (the parent service id), AUTONOMA_API_KEY. If your previews use Basic Auth, also add RENDER_PREVIEW_USER and RENDER_PREVIEW_PASS. 5) Open a PR and watch the workflow run.
```

## Project structure

```
.
├── .github/
│   └── workflows/
│       └── render-preview-e2e.yml
├── .gitignore
├── LICENSE
├── README.md
└── render.yaml
```

- `render.yaml` — Render Blueprint using the modern `previews.generation: automatic` schema.
- `.github/workflows/render-preview-e2e.yml` — GitHub Actions workflow that polls the Render API for a preview deploy and runs Autonoma E2E tests against it.

## About

This repository is maintained by [Autonoma](https://getautonoma.com) as reference material for the linked blog post. Autonoma builds autonomous AI agents that plan, execute, and maintain end-to-end tests directly from your codebase.

If something here is wrong, out of date, or unclear, please [open an issue](https://github.com/Autonoma-Tools/render-preview-environments/issues/new).

## License

Released under the [MIT License](./LICENSE) © 2026 Autonoma Labs.
