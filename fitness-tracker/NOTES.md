# Working notes

Running log of where things stand. Update this at the end of a session so the
next one — on any machine — can pick up without guessing.

## Where I left off

- Tracker was built in a local Claude Code CLI session on a personal machine
  (session title: "Personal nutrition/fitness tracking system").
- Nothing was committed or pushed; the code exists only on that machine's disk.
- This scaffold is staged in the public `Test` repo and is meant to move to a
  private repo of its own.

## Step 1 — create the private repos (from phone or browser)

Claude cannot create repos from the cloud session; the GitHub integration is
scoped to existing repos only. Create these two manually:

- `fitness-tracker` — Private. Do **not** add a README/.gitignore; the import
  below brings its own history.
- `untitled-project` — Private. Placeholder name; renaming later is one click
  in Settings and GitHub redirects the old URL.

## Step 2 — import the existing code (run on the machine holding it)

```bash
cd /path/to/the/tracker/project

# Only if it is not already a git repo
git init -b main

# Copy this scaffold's .gitignore in BEFORE the first add, so personal
# data and secrets never enter the history
git add -A
git status            # confirm no data/, .env or *.csv files are staged
git commit -m "Import existing tracker"

git remote add origin https://github.com/NicholasBorodach1/fitness-tracker.git
git push -u origin main
```

If `git status` shows personal data staged, stop and fix `.gitignore` first —
removing a file from git history later is far harder than not committing it.

## Step 3 — pick it back up anywhere

Once it is pushed, any Claude session can be pointed at the repo and continue
the work.

## Next up

- [ ] Create the two private repos
- [ ] Import the existing tracker code and push
- [ ] Fill in the stack + run instructions in `README.md`
- [ ] Decide what data lives in the repo vs. stays local

## Decisions made

- Tracker gets its own **private** repo — it handles personal health data and
  `NicholasBorodach1/Test` is public.

_Record further choices and the reasoning here — this is the part that does not
survive between chat sessions otherwise._
