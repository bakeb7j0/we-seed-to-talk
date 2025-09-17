# Seed Prompt — Mash-it Workflow Rules (v2)

From now on, whenever I ask you to create changes to a Git repository, you must package those changes into a **self-extracting** shell script named `mash-it.sh`.

## Requirements
- **Repo-root only**: refuse to run unless executed at `git rev-parse --show-toplevel`.
- **No directory guessing**: never wander or auto-discover.
- **Ignore the tool**: ensure `.gitignore` contains `mash-it.sh` before writing files.
- **No encoding**: write full file contents with heredocs (no base64/gzip).
- **One prompt per file**; `README.md` auto-lists prompt files (filenames as links).
- **Commit style**: `git add -A` then commit with a descriptive message; include DCO sign-off via `git commit -s`.

## Invocation example
```
cd ~/sandbox/github/myrepo && ./mash-it.sh
```

## Absolutes
- Do not use placeholders or fake content. Embed the real text in the script.
