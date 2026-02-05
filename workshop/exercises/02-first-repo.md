# First repo and first commit

```bash
mkdir my-first-repo
cd my-first-repo
git init
echo "# My First Repo" > README.md
git status
git add README.md
git status
git commit -m "Add README"
git log
```

Core loop: **stage** (`git add`) → **commit** (`git commit -m "message"`).
