Prepare and open a PR for the current work.

Steps:

1. **Identify the project type** — Look at the repo to determine the stack (Rails, Node, Python, etc.) and find the lint/test commands.

2. **Run linting** — Run the appropriate linter (rubocop, eslint, prettier, ruff, etc.). Fix any auto-fixable issues. If there are unfixable lint errors, stop and report them.

3. **Run related tests** — Identify which tests are relevant to the changed files and run them. If tests fail, stop and report the failures.

4. **Review all changes** — Run `git status` and `git diff` to understand the full scope of changes.

5. **Create atomic commits** — Break the work into logical, reviewable commits. Each commit should:
   - Be a single coherent change that a reviewer can understand in isolation
   - Have a clear, descriptive commit message (imperative mood, explain the "why")
   - Not bundle unrelated changes together

   For small changes, one commit is fine. For larger work, split into multiple commits (e.g., "Add User model", "Add user registration controller", "Add registration form view").

6. **Push to remote** — Push the branch to origin.

7. **Open a PR** — Use `gh pr create` with:
   - A clear title summarizing the change
   - A body with:
     - Link to the Linear ticket (if `.linear-ticket` exists)
     - Summary of what changed and why
     - Any notable implementation decisions
     - Testing notes if relevant

8. **Update Linear ticket** — If `.linear-ticket` exists in the repo root:
   - Mark the ticket as "In Review" using the Linear MCP tools
   - Attach the PR URL to the ticket as a link

Do NOT add co-author lines or "Generated with Claude Code" to commits or PR descriptions.
