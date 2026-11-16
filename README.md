# HoliPlanner

A simple trip planner that runs entirely in your web browser. Plan days, places, hotels and a budget in one page.

## How to use

Open the site at `https://<username>.github.io/HoliPlanner/` and start planning. Use "Add example trip" to see a sample.

## Your data stays with you

- Everything you enter is saved only in your own browser (localStorage) on your own device.
- Nothing is uploaded or sent anywhere. The page cannot make network requests.
- Clearing your browser data wipes your plans. Use **Export** regularly to keep a backup file.
- There is no sync between devices yet. Plans made on one device or browser do not appear on another.

## For the repo owner

Never commit exported plan files or screenshots of real plans. The `.gitignore` excludes common ones, but check before you commit.

## Publishing

See [RELEASING.md](RELEASING.md): the site updates only when a `v*` tag is pushed.
