# Build your academic website by vibecoding

A template for the 2026 Davis Lab retreat workshop: co-write a specification with an AI in VSCode, then have it build you a personal academic website — deployed free on GitHub Pages.

## How it works

Your CV data lives in [docs/cv.json](docs/cv.json). The plan for your site lives in [spec.md](spec.md). You and the AI fill in the spec together, then the AI builds `docs/index.html` from both. Data, plan, product — kept separate.

## Workshop steps

1. **Copy this repo** — click **Use this template → Create a new repository** (top-right on GitHub). Make it public.
2. **Open it in VSCode** — clone your new repo (VSCode: **Clone Git Repository**) and open the AI chat panel.
3. **Make cv.json yours** — replace Priya's details in `docs/cv.json` with your own. Paste your CV as plain text into the chat and ask the AI to do the conversion for you. Optionally drop a photo or images into `docs/assets/`.
4. **Co-write the spec** — open `spec.md` and fill in the `➡️ YOUR TURN` blanks, or ask the AI to interview you and fill them in. Then say: *"Read spec.md and docs/cv.json, ask me anything that's unclear, then build the site."*
5. **Deploy** — commit and push, then on GitHub: **Settings → Pages → Deploy from a branch → `main` / `docs`**. Your site appears at `https://<username>.github.io/<repo-name>/` in a minute or two.

> [!NOTE]
> A public repo is public: nothing in `cv.json` you wouldn't put on a conference poster — no phone numbers or home address.
> Bonus: name your repo exactly `<username>.github.io` and your site deploys to that root URL — one you'd happily put on a poster.

## Prerequisites

Complete these steps **before** the retreat.

### 1. Create a GitHub account

Sign up at [github.com/signup](https://github.com/signup) (free).

### 2. Install Git — Windows only

Download and run the installer from [git-scm.com/download/win](https://git-scm.com/download/win). Accept the default options.

macOS and Linux already have Git.

### 3. Install Visual Studio Code

Download from [code.visualstudio.com](https://code.visualstudio.com/download) and install.

### 4. Sign in to VSCode with GitHub

In VSCode, click the **Accounts** icon (bottom-left) → **Sign in with GitHub** → authorise in the browser.

### 5. Install the DeepSeek V4 extension

Install [DeepSeek V4 for Copilot Chat](https://marketplace.visualstudio.com/items?itemName=Vizards.deepseek-v4-for-copilot) (`Vizards.deepseek-v4-for-copilot`).

In VSCode: **Extensions** (`Ctrl+Shift+X` / `Cmd+Shift+X`) → search `Vizards.deepseek-v4-for-copilot` → **Install**.

### 6. Install the Live Server extension

Same as above: search `ritwickdey.LiveServer` in Extensions → **Install**. You'll use it to preview your site locally (right-click `docs/index.html` → **Open with Live Server**).
