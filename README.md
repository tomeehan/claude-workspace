# Project Workspace

A workspace for running parallel Claude Code sessions on a codebase.

## Setup

1. Copy `.workspace.example` to `.workspace`
2. Fill in your values:
   - `REPO_URL` — the git URL to clone
   - `DB_PREFIX` — prefix for isolated databases (e.g., `myapp_dev`)
3. Copy your `.env` secrets file into this directory

## Usage

Run `/start` to begin a new task. It will:
- Ask what you're working on
- Clone the repo into a new checkout
- Set up an isolated database
- Get you started

Multiple Claude sessions can run in parallel, each with their own checkout.

## Finishing up

Commit, push, open a PR. Leave the checkout in place.

Run `/cleanup` to remove checkouts with merged/closed PRs.
