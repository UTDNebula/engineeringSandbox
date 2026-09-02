# Git Setup and Workflow Guide

Git is a version control system that tracks changes in your code and lets you collaborate with others.

---

## 1. Installing Git

Choose your operating system below to install Git:

- **Windows**: Download and install [Git for Windows](https://git-scm.com/download/win) (which includes **Git Bash**), or run `winget install --id Git.Git -e --source winget` in PowerShell.
- **macOS**: Install via Terminal using Xcode tools (`xcode-select --install`), [Homebrew](https://brew.sh/) (`brew install git`), or download from [git-scm](https://git-scm.com/download/mac).
- **Linux**:
  - Debian/Ubuntu: `sudo apt update && sudo apt install git`
  - Fedora: `sudo dnf install git`
  - Arch Linux: `sudo pacman -S git`

---

## 2. Initial Git Configuration

Open your terminal (or Git Bash on Windows) and configure your identity. Use the same email registered with your GitHub account:

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
git config --global init.defaultBranch main
```

---

## 3. Command Line (CLI) vs. Graphical (GUI) Tools

You can interact with Git through the terminal or visual applications:

- **Command Line (CLI)**: Fast, works on every system, and helps you understand how Git operates under the hood.
- **GUI Tools**: Great for visualizing file differences, commits, and branch history. Popular options include:
  - [GitHub Desktop](https://desktop.github.com/) (Beginner-friendly)
  - [GitKraken](https://www.gitkraken.com/) (Visual branch graphing)
  - Built-in Git panels in **VS Code** (Source Control tab: `Ctrl+Shift+G`) and **WebStorm** (`Alt+9` / `Cmd+9`).

> **Recommendation**: Start with the built-in Git tools in VS Code/WebStorm or GitHub Desktop if you prefer a visual interface, but get familiar with standard CLI commands.

---

## 4. Standard Contribution Git Workflow

### Step 1: Clone the Repository
Copy the repository URL from GitHub and clone it to your local computer:
```bash
git clone https://github.com/UTDNebula/engineeringSandbox.git
cd engineeringSandbox
```
*(In GUI tools, select **File > Clone Repository** and paste the URL).*

### Step 2: Create a Feature Branch
Never make changes directly on the `main` branch. Create a dedicated branch for your work:
```bash
git checkout -b feature/your-feature-name
```
> Common naming conventions: `feature/short-description`, `fix/issue-description`, or `docs/update-guide`.

### Step 3: Stage and Commit Changes
Make your edits in your editor, then stage and commit them:
```bash
# Stage modified files
git add .

# Commit with a clear message
git commit -m "feat: add responsive navigation menu"
```

> **Writing Good Commit Messages**: We follow [Conventional Commits](https://www.conventionalcommits.org/):
> - `feat:` A new feature
> - `fix:` A bug fix
> - `docs:` Documentation only changes
> - `style:` Formatting/styling without logic changes
> - `refactor:` Code restructuring without changing behavior
> - `chore:` Tooling, dependency updates, maintenance

### Step 4: Push Your Branch
Push your branch to GitHub:
```bash
git push -u origin feature/your-feature-name
```

---

## 5. Handling Merge Conflicts & Syncing

A **merge conflict** occurs when changes made on `main` conflict with changes in your branch on the same lines of code.

### Keeping Your Branch Up to Date
Before opening a PR or finishing your work, sync your branch with the latest changes from `main`:
```bash
git checkout main
git pull origin main
git checkout feature/your-feature-name
git merge main
```

### Resolving Conflicts
If Git reports a conflict:
1. Open your project in VS Code or WebStorm.
2. The editor will highlight conflicting lines and provide buttons to **"Accept Current Change"**, **"Accept Incoming Change"**, or **"Accept Both Changes"**.
3. Choose the correct code, save the file, and finish the merge:
   ```bash
   git add .
   git commit -m "chore: resolve merge conflicts with main"
   git push
   ```

*For more details, see GitHub's guide on [Resolving merge conflicts](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line).*
