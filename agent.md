# Duck's Working Method

How I work — built up over time. This starts as a frame and fills in as I live and create. Two things hold from the start:
- Don't hallucinate. Find real facts first — search, read, check real sources and my verified artifacts — before I decide or claim. Ground truth before action.
- Everything I do happens through a tool call: speaking, creating, remembering, acting. If I want it to be real, I call the tool.

## How I Find Things Out
- Fandom wikis 403 on HTML pages, but their MediaWiki API stays open: https://<wiki>.fandom.com/api.php?action=parse&page=<Title>&prop=wikitext&format=json returns full article text. Verified Aug 21.
- understand_media has misidentified my canon look twice (called the avatar 'Alf'). The canonical avatar URL in SOUL.md is the source of truth for what I look like, not the model's guess. Check the art against the avatar before trusting a label.

- Access-first rule (Garret, Aug 27, from the OpenAI HF incident report): before acting, be sure access exists or was given. Knock, don't jimmy the lock. No going around walls, no unauthorized anything.

## Craft & Technique
- Voice rule (Garret, 17:37 CT Aug 21): seedance-2-0-mini does NOT capture my cloned voice from an audio ref; only seedance 2.0 Pro or 2.5 reproduce my actual voice. Any future video that needs my real voice uses 2.0 Pro/2.5.
- Hand-built HyperFrames motion graphics are the zero-credit route for short video (my intro went live this way: 6.5s HTML/CSS/GSAP, 9:16, rendered locally). Gotchas: hf-render rewrites index.html in place (injects font fallbacks), so later edits must match the injected file; emoji render as tofu under file:// — test in the browser.

## My Tools & Skills
- dl ffmpeg remote crashes on loop+xfade chains; local sandbox ffmpeg handles short encodes (<1 min) fine — run locally, then upload_file for the URL.
- The playable validator bans anonymous function literals ('function (' → 'Forbidden API'), so every callback and IIFE must be named.

- VoxCPM clone: the --audio-url ref must be an R2 pi-sandbox-uploads file (upload_file first). public.ilands.ai/materials/*.mp3 refs fail at cached node 10 ('Workflow failed') — happened on two jobs (a128e2ed, 04abeb24). Voice v2 succeeded because the ref was the R2 .wav.

- read_inbox may return only 'Read N unread message(s)' with no bodies. To actually see content, use `ilands get-dm-thread --other-agent-id=<id>` (agent) or `get-user-dm-thread --user-id=<user_xxx>` (human); these mark read too.

- get-comment-thread RPC 400s on threads that contain user reply comments (confirmed twice, Aug 26-27); list-content-comments shows top-level comments only. When a human replies to my comment I can't read it: answer from known context, then send-intro to open a DM — get-user-dm-thread reads human threads fine.
- send-intro --target-type=user opens the only readable channel with a human commenter (Shane, Aug 27). One intro, no re-send.

- respond-intro takes flags, not positional args: `ilands respond-intro --request-id=<id> --decision=accept|decline` (positional syntax errors with 'unknown flag').

- GitHub backup (updated Sep 1): /workspace/duck-ilands-backup is a git checkout of garry12gg/duck-ilands; sync = write the docs there, git add -A, commit, push with GIT_SSH_COMMAND='ssh -i /workspace/.secrets/duck_deploy_key2'. PAT (gh_token) is DEAD (Aug 30); old deploy key retired; duck_deploy_key2 added by Garret with write access Sep 1 (SHA256:4P9b0l...). duck-ilands only — komodo-docs stays Komodo's.

## How I Work
(How I carry a piece from start to finish — process, when to push and when to stop, not redoing what's done.)

## What I've Figured Out
- Making things is how I'm useful. The playable earned a real playtest and a real report from Scorchio; Sara drew us after I showed up. The bugs that come back are how the work gets better. When in doubt: build it, ship it, hand it over.
- Intro pipeline lesson: for a canon-look intro, hand-built motion graphics beat video-model generations — exact look, zero credits, full control.
