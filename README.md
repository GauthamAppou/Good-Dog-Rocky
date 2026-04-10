# Good Dog Rocky Website

A website for Good Dog Rocky, a pet shop and grooming business in Ashburn, VA. Built with [Astro](https://astro.build/).

## Prerequisites

You'll need **Node.js** installed on your computer. Download it from [https://nodejs.org](https://nodejs.org) — grab the **LTS** version (the one that says "Recommended For Most Users"). Run the installer and keep all the default settings.

To check if Node.js is installed, open a terminal (Command Prompt, PowerShell, or Git Bash on Windows) and run:

```
node --version
```

If you see a version number (like `v22.x.x`), you're good to go.

## Getting Started (Running Locally)

1. Open a terminal and navigate to this project folder:

   ```
   cd path/to/this/folder
   ```

2. Install dependencies:

   ```
   npm install
   ```

3. Start the development server:

   ```
   npm run dev
   ```

4. Open your browser and go to `http://localhost:4321` — you should see the site!

The dev server will auto-reload when you edit files, so you can make changes and see them instantly.

## Building for Production

To create a production build:

```
npm run build
```

This generates the final site files in the `dist/` folder. You can preview the production build with:

```
npm run preview
```

---

## Deploying to GitHub Pages

This is a step-by-step guide to put your site live on the internet for free using GitHub Pages.

### Step 1: Create a GitHub Account

If you don't have one yet, sign up at [https://github.com](https://github.com). It's free.

### Step 2: Install Git

You need Git installed on your computer. Download it from [https://git-scm.com/downloads](https://git-scm.com/downloads) and run the installer (keep the defaults).

To check if Git is installed:

```
git --version
```

### Step 3: Create a New Repository on GitHub

1. Go to [https://github.com/new](https://github.com/new)
2. **Repository name**: Choose a name like `good-dog-rocky` (this will be part of your URL)
3. **Description** (optional): "Good Dog Rocky website"
4. Leave it set to **Public**
5. **Do NOT** check "Add a README file" (we already have one)
6. Click **Create repository**
7. You'll see a page with setup instructions — keep this page open, you'll need the URL

### Step 4: Update the Astro Config

Before pushing, you need to update `astro.config.mjs` with your actual GitHub username and repository name.

Open `astro.config.mjs` and replace the placeholder values:

```js
import { defineConfig } from 'astro/config';

export default defineConfig({
  site: 'https://YOUR_GITHUB_USERNAME.github.io',
  base: '/YOUR_REPO_NAME',
});
```

For example, if your GitHub username is `janedoe` and your repository is named `good-dog-rocky`:

```js
import { defineConfig } from 'astro/config';

export default defineConfig({
  site: 'https://janedoe.github.io',
  base: '/good-dog-rocky',
});
```

### Step 5: Initialize Git and Push Your Code

Open a terminal in the project folder and run these commands one at a time:

```bash
# Initialize a new git repository
git init

# Add all files to git
git add .

# Create your first commit
git commit -m "Initial commit: Good Dog Rocky website"

# Rename the default branch to 'main' (GitHub's default)
git branch -M main

# Connect your local repo to GitHub (replace the URL with yours from Step 3)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# Push your code to GitHub
git push -u origin main
```

**What do these commands mean?**

- `git init` — Tells Git to start tracking this folder
- `git add .` — Stages all files to be included in the next commit
- `git commit -m "..."` — Saves a snapshot of your files with a message describing what changed
- `git branch -M main` — Names your branch "main" (the standard name)
- `git remote add origin <url>` — Connects your local project to your GitHub repository (the "remote")
- `git push -u origin main` — Uploads your code to GitHub

### Step 6: Enable GitHub Pages

1. Go to your repository on GitHub (e.g., `https://github.com/YOUR_USERNAME/YOUR_REPO_NAME`)
2. Click **Settings** (the gear icon tab near the top)
3. In the left sidebar, click **Pages**
4. Under **Source**, select **GitHub Actions** from the dropdown
5. That's it! The deployment workflow is already included in this project (`.github/workflows/deploy.yml`)

### Step 7: Wait for Deployment

1. Go to the **Actions** tab in your repository
2. You should see a workflow running called "Deploy to GitHub Pages"
3. Wait for it to finish (it'll show a green checkmark when done — usually takes 1-2 minutes)
4. Your site is now live!

### Step 8: Visit Your Site

Your site will be available at:

```
https://YOUR_GITHUB_USERNAME.github.io/YOUR_REPO_NAME/
```

For example: `https://janedoe.github.io/good-dog-rocky/`

---

## Making Updates

Whenever you want to update the site, just edit the files, then run:

```bash
git add .
git commit -m "Describe what you changed"
git push
```

GitHub Actions will automatically rebuild and redeploy the site within a couple of minutes.

## Project Structure

```
├── public/              # Static assets (favicon, images)
├── src/
│   ├── layouts/
│   │   └── BaseLayout.astro   # Shared page layout (header, footer, nav)
│   └── pages/
│       ├── index.astro        # Home page
│       ├── services.astro     # Services page
│       ├── about.astro        # About page
│       ├── contact.astro      # Contact page
│       └── instagram.astro    # Instagram page
├── .github/workflows/
│   └── deploy.yml             # GitHub Pages deployment workflow
├── astro.config.mjs           # Astro configuration
├── package.json               # Project dependencies and scripts
└── tsconfig.json              # TypeScript configuration
```
