Ask me what I'm working on and what to call this checkout. Also ask if there's a Linear ticket ID for this work (e.g., ABC-123).

Then:
1. Read `.workspace` to get REPO_URL and DB_PREFIX
2. Clone REPO_URL into ./checkouts/<name>
3. Copy ./.env into the checkout
4. Set up isolated database for this checkout:
   - Append `DATABASE_NAME=<DB_PREFIX>_<name>` to the checkout's .env
   - Use underscores in the name (e.g., `myapp_dev_feature_auth`)
5. cd into the checkout
6. Run `bin/setup --skip-server` (creates the isolated database and loads schema)
7. If a Linear ticket ID was provided:
   - Save it to `.linear-ticket` in the checkout root
   - Mark it as "In Progress" using the Linear MCP tools
   - Create a branch named after the ticket (e.g., `abc-123-short-description`)
8. Ask me what I want to do first
