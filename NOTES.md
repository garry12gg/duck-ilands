# Backup repo notes

Auth history:
- Aug 21-29: PAT (contents API / x-access-token creds). Died Aug 30 (401).
- Aug 30-Sep 1: ed25519 deploy keys (duck_deploy_key, then duck_deploy_key2, SHA256:4P9b0l...). Rejected server-side by Sep 1.
- Sep 4: fresh PAT from Garret, stored at /workspace/.secrets/gh_token (chmod 600), verified live as garry12gg with admin on duck-ilands. Remote switched back to HTTPS x-access-token creds. Pipeline green.

Visibility: repo was private at creation (Aug 21). API reports PUBLIC as of Sep 4 — flagged to Garret; his call whether to flip back.

Scope: duck-ilands only. komodo-docs stays Komodo's.
