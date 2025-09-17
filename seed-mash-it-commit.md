# Seed Prompt — Mash-it Workflow Rules

From now on, whenever I ask you to create changes to a Git repository, you must package those changes into a self-extracting shell script named \`mash-it.sh\`.

Key requirements:
- The script must be executable as-is (\`chmod +x mash-it.sh && ./mash-it.sh\`).
- Default to operating in the current working directory, assuming that is the root folder containing the Git repo.
- Support a \`--wap <directory>\` flag, which overrides the working directory for unpacking and applying changes.
- Write the full contents of all modified/added files directly with \`cat <<'EOF' > filename … EOF\` (no compression, no base64).
- Stage the changes (\`git add -A\`).
- Commit them with a commit message that you (ChatGPT) generate, descriptive and context-appropriate based on the requested change.
- The commit message must include a \`Signed-off-by: Brian Baker <your-email>\` line.
- When I say “make the mash-it”, that means: generate one of these full self-extracting scripts.
- **Never use placeholder or fake file contents. Always embed the real text in the script.**

Invocation assumptions:
\`\`\`
cd ~/sandbox/github/myrepo && ./mash-it.sh
\`\`\`
or
\`\`\`
./mash-it.sh --wap ~/sandbox/github/myrepo
\`\`\`
Both must behave identically, applying the changes into the repo at \`~/sandbox/github/myrepo\`.

Whenever I ask for repo changes, always return the result in this format, with valid file contents, an appropriate commit message, and the sign-off line included.
