# Project Workspace

This is a workspace for running parallel Claude Code sessions on a codebase.

## Structure

- `.env` — shared secrets, copy into any new checkout
- `.workspace` — project-specific config (repo URL, database prefix)
- `checkouts/` — where repo clones live

## How it works

Use /start to begin. It will ask what you're working on, clone the repo into a new checkout, set it up, and get going.

Multiple Claude sessions can run in parallel from this folder, each with their own checkout.

## Finishing up

Commit, push, open a PR. Leave the checkout in place.
