# 🚀 Vue.js CI/CD Deployment on GitHub Pages (via Node script)

This project demonstrates how to set up a **Vue 3 + Vite** project using **Bun** or **Node.js**, with automated deployment to **GitHub Pages** using a custom Node.js script (`deploy-gh-pages.mjs`) and GitHub Actions.

> 📡 Live Demo: [https://BaseMax.github.io/vuejs-cicd-deploy-on-github-pages](https://BaseMax.github.io/vuejs-cicd-deploy-on-github-pages)

---

## 📦 Tech Stack

- ⚡ [Vue 3](https://vuejs.org/)
- ⚗️ [Vite](https://vitejs.dev/)
- 🧪 [Bun](https://bun.sh/) or [Node.js](https://nodejs.org/)
- 🌀 Custom GitHub Pages deploy script
- 🛠 GitHub Actions CI/CD

---

## 🧪 Development

Run locally with **Bun**:

```bash
bun install
bun run dev
```

Or with npm:

```bash
npm install
npm run dev
```

## 🚀 Deployment

This project uses a custom Node.js script to deploy the built app to the `gh-pages` branch.

## ▶ Manual Deploy

```bash
npm run deploy
```

This runs deploy-gh-pages.mjs which:

- Builds the project using vite build
- Creates an orphan gh-pages branch
- Commits the `dist/` folder
- Force-pushes it to GitHub
- Cleans up local state

## ▶ GitHub Actions CI/CD

Automatic deployment is also set up via .github/workflows/deploy.yml. On every push to main, it:

- Installs dependencies
- Runs the deploy script (npm run deploy)
- No manual steps are needed after a push to main.

## 📁 Directory Structure

```bash
.
├── .github/workflows/deploy.yml   # GitHub Actions CI/CD
├── deploy-gh-pages.mjs            # Node.js deploy script
├── src/                           # Vue app source code
├── dist/                          # Auto-generated after build
├── index.html
├── vite.config.ts
└── package.json
```

## 🛠 Scripts in package.json

```json
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "deploy": "node deploy-gh-pages.mjs"
  }
}
```

## 🔐 Notes

Make sure GitHub Pages is enabled in repo settings:

- Branch: gh-pages
- Folder: / (root)

This repo is set to private: `"private": true` (optional for public sharing)

You need write access for pushing to `gh-pages`.

## 👤 Author

Seyyed Ali Mohammadiyeh (Max Base)

📬 maxbasecode@gmail.com

🔗 https://github.com/BaseMax

## 🪪 License

MIT
