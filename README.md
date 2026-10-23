# LEARNING-ROADMAP-VIBE

### CI workflow - minimal

🏁 develop ➡️ deploy ➡️ main 🎉

More details : 

- **develop**: on every push, checks that `index.html` exists, the JavaScript is valid...
  *Security:* Dependabot (alerts, security fixes, weekly action updates with a 7-day cooldown), CodeQL (JS + workflows), secret scanning, read-only permissions.
- **deploy**: on every push, rebuilds, then advances `main` and creates a version tag.
  *Security:* write access limited to the promotion job only, no force-push (fast-forward only), `main` moves only if the build passes.
- **main**: on every tag, writes the version into `version.json` and publishes the site to GitHub Pages.
  *Security:* only tags trigger publishing, Pages permissions scoped to this job, `github-pages` environment restricted to tags.
