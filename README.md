# Git + GitHub Cheat Sheet

**PowerShell:** Git commands · **VS Code:** edit files · **GitHub:** host repositories and review pull requests

## One-time setup

Sign in to GitHub CLI:

```powershell
gh auth login
```

Set the name shown on your commits:

```powershell
git config --global user.name "Your Name"
```

Set the email shown on your commits. Use an email associated with GitHub, including your `noreply` address:

```powershell
git config --global user.email "you@example.com"
```

## Get a repository

Go to the folder where you keep your projects:

```powershell
cd $HOME\Documents\repos
```

Clone a repository. Replace the URL with its GitHub HTTPS URL:

```powershell
git clone https://github.com/OWNER/REPOSITORY.git
```

Move into the downloaded repository:

```powershell
cd REPOSITORY
```

Open the folder in VS Code:

```powershell
code .
```

## Start work

Switch to the default branch and get the latest changes:

```powershell
git switch main
```

```powershell
git pull
```

Create a branch for your change. Replace `BRANCH-NAME` with a short, descriptive name:

```powershell
git switch -c BRANCH-NAME
```

Edit and save files in VS Code. Check what changed:

```powershell
git status
```

Review your edits:

```powershell
git diff
```

Stage a specific file (replace `FILE` with its path):

```powershell
git add FILE
```

Stage all changes in the current directory:

```powershell
git add .
```

Review staged changes:

```powershell
git diff --staged
```

Commit with a short description:

```powershell
git commit -m "Describe the change"
```

Push your branch to GitHub:

```powershell
git push -u origin BRANCH-NAME
```

## Suggested naming conventions

- Use `type/short-description` for branches, such as `feat/add-search`.
- Use `type: description` for commit messages and PR titles, such as `feat: add filters`.
- Keep descriptions concise; use lowercase and hyphens in branch names.

Common types:

| Type | Use for |
| --- | --- |
| `feat` | A new feature or capability |
| `fix` | A bug fix |
| `docs` | Documentation-only changes |
| `style` | Formatting or code style; no behavior change |
| `refactor` | Code restructuring without changing behavior |
| `perf` | Performance improvements |
| `test` | Adding or updating tests |
| `build` | Build system or dependency changes |
| `ci` | CI configuration and automation |
| `chore` | Maintenance tasks that do not fit another type |
| `revert` | Reverting an earlier change |

## Open and review a pull request

- On GitHub, create a PR from your branch into the repository’s default branch (often `main`).
- Describe what changed and review the diff before merging.
- After merging, update your local default branch before starting your next change.

## Resolve a simple conflict on GitHub

- Open the conflicted PR and select **Resolve conflicts** (if available).
- Keep the agreed changes and remove conflict markers.
- Select **Mark as resolved**, then **Commit merge**.
- For complex conflicts, resolve locally and push the updated branch.

## Copilot in VS Code

- Sign in to GitHub and open Copilot Chat.
- Ask it to explain code or suggest a change.
- Review suggestions; they can be wrong.

**Workflow:** update default branch → create branch → edit → review → stage → commit → push → PR

## Project: After Hours Arcade — Pong

A small, dependency-free Pong game that runs in your browser.

### Play

Open `index.html` in a modern browser and select **Start game**. No install or build step is needed.

- Move your paddle with **W / S** or **↑ / ↓**. On touch screens, use the on-screen buttons.
- Press **Space** or select **Pause** to pause and resume.
- Choose Easy, Normal, or Hard CPU difficulty before or during a game.
- First to seven points wins. Select **Restart** to reset the match.
