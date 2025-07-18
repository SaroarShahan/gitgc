# 🚀 @saroarshahan/gitgc

A lightweight CLI tool that automates `git add`, `git commit`, and `git push` — with optional flags for flexibility.

---

### 📦 Installation

```bash
yarn add @saroarshahan/gitgc
```

### 🛠️ Usage

```bash
yarn gitgc "your commit message" [--options]
```

### 🔧 Options

| Flag           | Description                                         | Default  |
| -------------- | --------------------------------------------------  | -------- |
| `--files`      | Specify files or folders to stage                   | `.`      |
| `--remote`     | Git remote to push to                               | `origin` |
| `--branch`     | Git branch to push to                               | `main`   |
| `--amend`      | Amend the last commit instead of creating a new one | `false`  |
| `--no-push`    | Skips the `git push` step                           | `false`  |
| `--push-only`  | Skip staging/commit. Only pushes to remote branch.  | `false`  |
| `-h`, `--help` | Show help information                               |          |

### 🧪 Final Behavior
| Use Case                  | Outcome                             |
| ------------------------- | ----------------------------------- |
| User has Husky configured | Hooks run automatically             |
| User adds `--no-verify`   | Hooks are skipped using `git` flags |
| User has no Husky         | CLI works as usual                  |


### 📝 Examples

```bash
# Simple commit and push
yarn gitgc "fix: resolve issue with DataTable filter state"

# Commit specific file
yarn gitgc "style: update item alignment in CSS" --files src/header.css

# Amend the previous commit and skip push
yarn gitgc "fix: reword commit" --amend --no-push

# Push to different remote and branch
yarn gitgc "feat: deploy script added" --remote origin --branch dev

# Skip hooks (e.g., Husky)
gitgc "fix: skip hooks" --no-verify

# Interactive mode (no commit message)
yarn gitgc
```

### 🔍 Features
- Prompt-based fallback if no message is provided
- Checks for uncommitted changes before committing
- Safe defaults with room for customization
- Clean CLI experience with color-coded output
- By default, `gitgc` respects all Git hooks (like Husky’s `pre-commit`, `commit-msg`, `pre-push`).

### 🧑‍💻 Author

**Saroar Shahan**  
[GitHub](https://github.com/SaroarShahan) • [NPM](https://www.npmjs.com/~saroarshahan)

### 📄 License
MIT License