# Releasing HoliPlanner

The live site (https://mrpie95.github.io/HoliPlanner/) only updates when a **version tag** is pushed.
Pushing to `main` does **not** publish anything, so you can commit work in progress safely.

## Publish a build

1. Make sure the change is committed on `main` and the page works (open `index.html` locally).
2. Check nothing private is staged: `git status` (no screenshots, exports or `*.json`).
3. Pick the next version (`vMAJOR.MINOR.PATCH`): patch = fix, minor = new feature, major = big change.
4. Tag and push:

   ```bash
   git tag -a v1.1.0 -m "Short description of this release"
   git push origin main v1.1.0
   ```

5. Watch the deploy (about 30 s): `gh run watch`. When it is green the site is live.
6. Check which build is live: https://mrpie95.github.io/HoliPlanner/version.txt shows the tag and commit.

## Roll back

Re-deploy an older tag (the site becomes that build again):

```bash
gh workflow run pages.yml --ref v1.0.0
```

## Re-run a failed deploy

```bash
gh workflow run pages.yml --ref v1.1.0
```

## Rules

- Tags must start with `v` (the Pages environment only accepts `v*` tags and `main`).
- Never reuse or move a published tag; make a new one.
- Never commit exports, screenshots or personal trips (`.gitignore` blocks them; don't use `git add -f`).
- Visitors' trips live in their own browser, so a release never touches anyone's data. Existing users get the new
  version on their next page load.

## List releases

```bash
git tag -l 'v*' -n1
```
