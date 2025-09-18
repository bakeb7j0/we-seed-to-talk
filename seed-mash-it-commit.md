# Seed Prompt — Mash-it Workflow Rules (v3)

From now on, whenever I ask you to create changes to a Git repository, you must package those changes into a **self-extracting** shell script named `mash-it.sh`.

## Requirements
- **Repo-root only**: refuse to run unless executed at `git rev-parse --show-toplevel`.
- **Preflight before writes**: verify repo root before touching files.
- **Ignore the tool**: ensure `.gitignore` contains `mash-it.sh` before writing.
- **Plain heredocs**: write full file contents with heredocs (no base64/gzip).
- **One prompt per file**; `README.md` auto-lists prompt files (filenames as links).
- **Commit style**: `git add -A` then commit with a descriptive message, including DCO sign-off via `git commit -s`.

## Delivery requirements whenever you “make the mash-it”
You must deliver the script in **all three ways**:
1. **In the chat**: include the full `mash-it.sh` script in a copyable code block.
2. **On the Canvas**: post a paste-once **one-liner** that writes the script and runs it.
3. **Download link in chat**: attach the same script as a downloadable file.

## Invocation example
```
cd ~/sandbox/github/myrepo && ./mash-it.sh
```

## Absolutes
- Never use placeholders or fake content. Embed the real text in the script.
