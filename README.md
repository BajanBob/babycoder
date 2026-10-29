# Coder for Babies

A step-by-step "GPS" that walks a beginner from a project name to a published GitHub release with installers for Windows, macOS, Linux, Raspberry Pi, Android and iOS.

## Run it

- **Easiest:** open `index.html` in any web browser. No install needed.
- **Put it online:** commit `index.html` to a GitHub repo and turn on GitHub Pages (Settings → Pages → Deploy from branch → main).

## The route

1. GitHub username
2. Project name, description, public/private, project type
3. Create the repository (pre-filled GitHub link)
4. Drop files (drag files or a whole folder)
5. Commit to main (upload page, or one-click per-file commits)
6. Code check: finds errors, fills the delete box with the file name, highlights the bad line, then delete and recommit
7. Build recipe (`.github/workflows/build.yml`) plus starter files
8. Version and tag
9. Pre-release or publish (locked until the code check passes)
10. Download installers
11. Share and deploy: collaborators, Codespaces, Cloudflare, Render, Vercel, Netlify, crates.io

A Git toolbox explains `git init`, `add`, `commit`, `push`, `tag`, `restore`, `reset --soft HEAD~1`, `switch`, `merge` and `log --graph`, with your project's names filled in.

## Claude review

Claude reviews the code only when the page is opened inside Claude (the published artifact). Opened from this zip on its own, the page runs the built-in quick check instead. The quick check catches common typos, broken JSON, tabs in YAML, leftover merge markers and pasted secret keys. Releases stay locked until Claude approves, so use the Claude version of the page for step 6 and step 9.

## Make it your own (modular)

Every step is one entry in the `STEPS` list inside `index.html`. Each entry has:
- `id` and `title`
- `isDone()` or `manual: true`
- `gps()`, which returns the next-turn text and link
- `render()`, which returns the panel HTML

Add an entry to add a stop to the route. Build recipes are the `<script type="text/plain" id="tpl-...">` blocks; add a new one and list it in `TYPES`.

Progress is saved in your browser only.
