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

## UI Copy

Use neutral, object-first UI copy (e.g., Settings, Files, Update password). Only use "your" if removing it causes confusion.

## ViewComponents

Use slots for content that renders as UI (text, HTML, other components). Use args for logic and behavior (booleans, options, configuration).

```ruby
# Good - slots for UI content
renders_one :label
renders_one :value

# Good - args for logic
def initialize(variant: :default, disabled: false)

# Bad - args for UI content
def initialize(label:, value:)
```
