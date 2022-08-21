![GitHub Workflow Build](https://github.com/Zen-Railz/Frontend/actions/workflows/main.yaml/badge.svg?branch=main)

![ZenRailz Frontend Logo](images/logo.svg)

# Overview

This is the frontend repository of our application.
| Domain | Description |
|-|-|
| Repository | [GitHub](https://github.com/Zen-Railz/Frontend) |
| Language | [Node.js with TypeScript](https://nodejs.dev/en/learn/nodejs-with-typescript) |
| Framework | [Next.js](https://nextjs.org/) |
| Hosting | [Heroku with Docker](https://devcenter.heroku.com/articles/container-registry-and-runtime) |
| UI/UX | [Figma](https://www.figma.com/)

## Prerequisite

Ensure that [node.js](https://nodejs.org/en/) is installed.

## Initialization

This section documents the steps taken when this repository was set-up for the first time. You do not have to perform these actions.

In the root directory of this repository, create a new Next.js project with TypeScript by running:
```
npx create-next-app@latest --ts
```
Follow on-screen instructions to provide the project name.

## Development

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

## Deployment

Create a `Dockerfile` in the root directory of this repository. You may take reference from this [sample](https://github.com/vercel/next.js/blob/canary/examples/with-docker/Dockerfile).

Add this configuration to the `next.config.js` file:
```javascript
module.exports = {
  // ... rest of the configuration.
  output: 'standalone',
}
```

In the `package.json` file, add the start command in the scripts section:
```
"scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start -p $PORT"
  }
```

To leverate on [GitHub Actions](https://github.com/features/actions), add a `main.yaml` file to `/.github/workflows` directory.

Get your API Key from Heroku and add it to your repository secrets in GitHub.

<details>
    <summary>Getting API Key from Heroku</summary>
    <ol>
        <li>Login to <a href="https://www.heroku.com/">Heroku</a></li>
        <li>Navigate to Account settings</li>
        <li>Look for the API Key section and click on the reveal button</li>
    </ol>
</details>
<details>
    <summary>Adding a secret to GitHub Repository</summary>
    Refer to the section on <a href="https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository">Creating encrypted secrets for a repository</a>.
</details>
