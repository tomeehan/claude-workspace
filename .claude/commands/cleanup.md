Clean up checkouts that have merged or closed PRs.

For each checkout in ./checkouts/:
1. Get the current git branch name
2. Check if there's a PR for that branch using `gh pr view <branch> --json state`
3. If the PR is merged or closed:
   - List the databases to be dropped (based on DATABASE_NAME in .env)
   - Drop the databases (primary, cache, queue, cable, and test)
   - Delete the checkout directory
4. If no PR exists or PR is still open, skip it

Before deleting anything, show a summary of what will be cleaned up and ask for confirmation.

Example output:
```
Checking checkouts...

feature-auth:
  Branch: feature/add-auth
  PR #9: MERGED
  Databases: myapp_dev_feature_auth, myapp_dev_feature_auth_cache, ...
  → Will be deleted

bugfix-login:
  Branch: fix/login-issue
  PR #12: OPEN
  → Skipping (PR still open)

old-experiment:
  Branch: experiment-branch
  No PR found
  → Skipping (no PR)

Ready to delete 1 checkout and drop 5 databases. Proceed? (y/n)
```

Only proceed with deletion after user confirms.
