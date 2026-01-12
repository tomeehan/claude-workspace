Prepare and open a PR for the current work.

Do not commit or push to main.

Steps:

1. **Run /commit** — Execute the /commit command to create atomic commits.

2. **Push to remote** — Push the branch to origin.

3. **Open a draft PR** — Use `gh pr create --draft` with:
   - A clear title summarizing the change
   - A body with:
     - Link to the Linear ticket (if `.linear-ticket` exists)
     - Summary of what changed and why
     - Any notable implementation decisions
     - Testing notes if relevant

4. **Update Linear ticket** — If `.linear-ticket` exists in the repo root:
   - Mark the ticket as "In Review" using the Linear MCP tools
   - Attach the PR URL to the ticket as a link