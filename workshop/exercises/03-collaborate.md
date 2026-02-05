# Remote, push, and collaboration

**Add remote and push (use your repo URL):**

```bash
git remote add origin https://github.com/yourname/my-first-repo.git
git branch -M main
git push -u origin main
```

**Branches:**

```bash
git switch -c add-license
echo "MIT License" > LICENSE.txt
git add LICENSE.txt
git commit -m "Add LICENSE"
git switch main
git merge add-license -m "Merge add-license"
git push
```

**Collaboration:** Pull before you start, push when you finish. Resolve conflicts by editing the file (remove `<<<<<<<`, `=======`, `>>>>>>>`) then `git add` and `git commit`.
