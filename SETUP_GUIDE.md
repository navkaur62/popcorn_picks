# 🛠️ VS Code Setup Guide — Popcorn Picks

A step-by-step guide to run this project locally in VS Code and deploy it to GitHub.

---

## PART 1: Setting Up VS Code

### Step 1 — Install Required Software

Download and install these (if not already installed):

| Tool | Download Link |
|------|--------------|
| Python 3.10+ | https://www.python.org/downloads/ |
| VS Code | https://code.visualstudio.com/ |
| Git | https://git-scm.com/downloads |

> ✅ During Python install, check **"Add Python to PATH"**

---

### Step 2 — Install VS Code Extensions

Open VS Code → press `Ctrl+Shift+X` → search and install:

| Extension | Why |
|-----------|-----|
| **Python** (Microsoft) | Python language support |
| **Jupyter** (Microsoft) | Run .ipynb notebooks inside VS Code |
| **Pylance** | Better Python autocomplete |
| **GitLens** | Powerful Git history view |
| **Live Server** | Preview index.html in browser |
| **Rainbow CSV** | View CSV files nicely |

---

### Step 3 — Open the Project

```bash
# In terminal / command prompt:
cd path/to/Popcorn-Picks
code .
```

Or: **File → Open Folder** → select the `Popcorn-Picks` folder.

---

### Step 4 — Create a Virtual Environment

Open the VS Code terminal (`Ctrl+`` `) and run:

```bash
# Create virtual environment
python -m venv venv

# Activate it:
# Windows:
venv\Scripts\activate

# macOS / Linux:
source venv/bin/activate
```

You'll see `(venv)` appear in your terminal — that means it's active.

---

### Step 5 — Install Dependencies

```bash
pip install -r requirements.txt
```

Wait for all packages to install. You should see something like:
```
Successfully installed numpy-1.26.0 pandas-2.1.0 matplotlib-3.8.0 seaborn-0.13.0 ...
```

---

### Step 6 — Select the Python Interpreter

- Press `Ctrl+Shift+P` → type **"Python: Select Interpreter"**
- Choose the one that shows `./venv/bin/python` or `.\venv\Scripts\python.exe`

---

### Step 7 — Run the Jupyter Notebook

1. In the Explorer panel, open `notebook/Popcorn_Picks.ipynb`
2. Click **"Select Kernel"** (top right) → choose your venv Python
3. Press **Run All** (▶▶) or run cells one by one with `Shift+Enter`

---

### Step 8 — Preview the Website

1. Right-click on `index.html` in the Explorer
2. Select **"Open with Live Server"**
3. Your browser opens at `http://127.0.0.1:5500/index.html` 🎉

> If Live Server isn't available, just double-click `index.html` — it opens directly in your browser.

---

## PART 2: Uploading to GitHub

### Step 1 — Create a GitHub Account
Go to https://github.com and sign up (free).

---

### Step 2 — Create a New Repository

1. Click **"+"** → **"New repository"**
2. Name it: `Popcorn-Picks`
3. Set to **Public**
4. ❌ Do NOT initialize with README (you already have one)
5. Click **"Create repository"**

---

### Step 3 — Configure Git in Terminal

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

---

### Step 4 — Initialize and Push

```bash
# Inside your project folder:
git init
git add .
git commit -m "🎬 Initial commit — Popcorn Picks Movie Analysis"

# Connect to GitHub (replace with YOUR URL):
git remote add origin https://github.com/yourusername/Popcorn-Picks.git
git branch -M main
git push -u origin main
```

---

### Step 5 — Enable GitHub Pages (Free Website Hosting)

1. Go to your repo on GitHub
2. Click **Settings** tab
3. Scroll to **"Pages"** in the left sidebar
4. Under **Source**: select **"Deploy from a branch"**
5. Branch: **main**, Folder: **/ (root)**
6. Click **Save**

After 1–2 minutes your site is live at:
```
https://yourusername.github.io/Popcorn-Picks/
```

---

### Step 6 — Future Updates (Push Changes)

Every time you make changes:
```bash
git add .
git commit -m "✨ Update: description of what you changed"
git push
```

---

## 📁 Final Folder Structure in VS Code

```
Popcorn-Picks/              ← Root folder (open this in VS Code)
│
├── 📁 data/
│   └── mymoviedb.csv       ← Dataset
│
├── 📁 notebook/
│   └── Popcorn_Picks.ipynb ← Open this in VS Code Jupyter
│
├── 📁 images/              ← Chart exports from notebook
│
├── 📄 index.html           ← Right-click → Open with Live Server
├── 📄 README.md            ← Shown on GitHub automatically
├── 📄 requirements.txt     ← pip install -r requirements.txt
├── 📄 .gitignore
└── 📄 SETUP_GUIDE.md       ← This file!
```

---

## ❓ Troubleshooting

| Problem | Solution |
|---------|----------|
| `python` not found | Reinstall Python, check "Add to PATH" |
| `pip` not found | Run `python -m pip install ...` instead |
| Jupyter kernel not found | Run `pip install ipykernel` then select venv kernel |
| Charts not showing in notebook | Run `%matplotlib inline` at top of notebook |
| Git push rejected | Run `git pull origin main --rebase` first |

---

*Happy coding! 🍿*
