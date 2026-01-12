Prepare atomic commits for the current work.

Do not commit or push to main.

Steps:

1. **Run related tests** — Identify which tests are relevant to the changed files and run them. If tests fail, stop and report the failures.

2. **Create backup** — Commit everything as "WIP: backup before atomic commits", then `git reset --soft HEAD~1`. This gives the user a recoverable snapshot in reflog. Do not use reflog yourself — if something goes wrong, stop and let the user recover manually.

3. **Gather context** — Ask the user:
   - What is this work for? (feature, bug fix, refactor, etc.)
   - Any business context that should be captured in commit messages?
   - Is there a ticket or issue number to reference?

4. **Plan commits** — Optimise for diff clarity. A reviewer reads diffs, not files.

   Rules:
   - One change per commit (if you'd say "and" to describe it, split it)
   - Never break the build
   - Introduce before use (define it in one commit, call it in the next)

   Example:
   1. Introduce PostScoped concern (empty module)
   2. Define #set_post
   3. Call #set_post in before_action
   4. Introduce DraftsController (empty spec)
   5. Include PostScoped
   6. Authorise index with PostPolicy
   7. Implement index action

   Bad:
   - "Add DraftsController with all functionality" — wall of changes
   - Calling #set_post before defining it — diff references something that doesn't exist

   For trivial changes, one commit is fine.

5. **Evaluate PR size** — If the plan exceeds 300 lines diff or 7 commits, present this to the user. They will decide how to split it into multiple PRs.

6. **Confirm with user** — Present the planned commits (title + description for each) and wait for approval before proceeding. Commit descriptions should include relevant business context.

7. **Create commits** — Execute the approved plan. Use `git add -p` to stage hunks surgically when changes need to be split across commits.