# AGENTS.md — canfar-skills

OpenCADC CANFAR Science Platform skills for agents. Source of truth is current
OpenCADC implementation (client, Skaha, Helm templates), then live site output.

## Remotes (AstroAI fork workflow)

| Remote | Points at | Use |
|--------|-----------|-----|
| `origin` | `sfabbro/canfar-skills` | Push `wip/*` only |
| `upstream` | `astroai/canfar-skills` | Sync `main`; PR target |

`main` tracks `upstream/main`. Do not push feature branches to `astroai`.

```bash
git fetch upstream && git rebase upstream/main
git checkout -b wip/<topic>
git push -u origin HEAD
gh pr create -R astroai/canfar-skills --head sfabbro:$(git branch --show-current)
```

## Verification

After skill or catalog edits:

```bash
python3 scripts/validate_skills.py
```
