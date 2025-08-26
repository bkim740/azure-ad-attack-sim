# Publish to GitHub

```bash
# in the directory that contains this folder
cd azure-ad-attack-sim

git init
git add .
git commit -m "chore: scaffold project"
git branch -M main
git remote add origin https://github.com/<your-username>/azure-ad-attack-sim.git
git push -u origin main
```

## Commit Style
- `feat:` for new content, `docs:` for documentation, `chore:` for housekeeping.
- Keep screenshots sanitized and small (<1MB each).
