# GenAI Symposium App

Presentation app for the School of Arts and Culture Research and Scholarly Activity Symposium, 28 July 2026.

## What's in here

- `index.html`, the 16-slide app, unchanged from the current build
- `pages/`, the five standalone activity pages, currently duplicated here as backup and as a next step
- This README

## Step 1, get it hosted (do this first)

1. Create a new repo on GitHub, public
2. Upload `index.html` and the `pages/` folder to the repo root
3. Go to Settings, Pages
4. Under "Source" choose the `main` branch, root folder
5. Save, wait a minute or two for the first build
6. Your URL will be `https://[your-username].github.io/[repo-name]/`

That URL is what goes on the QR code on slide 2.

## Step 2, test the diagnosis

Once it's live, open the URL and press the right arrow key.

- If the slides change, the app is working and the embedded pages should now open too, since https removes the restriction that blocks them locally
- If nothing happens, something else is wrong and worth another look before the symposium

## Step 3, optional but worth it, unembed the five pages

Right now the five activity pages are base64-encoded inside `index.html`, which is why the file is heavy and slow, especially over conference wifi. Once hosted, this isn't necessary, since a linked file loads over https like any other page.

The five pages are already sitting in `pages/` for exactly this. To switch:

1. In `index.html`, find the `EMBED` object in the script near the bottom
2. Replace the base64 `openEmbed()` logic with a simple `window.open()` or a link to the matching file in `pages/`, for example `pages/3-session-builder.html`
3. This drops the file from about 680KB total down to roughly 30KB for `index.html` alone, everything else loads on demand

Not done yet, this is the next session's work.

## Still open

- QR code for slide 2, waiting on the live URL from Step 1
- Length, current run measured at 40 minutes against a 15 to 20 minute slot, needs a cut
- Screenshot placeholders in Activity 4, for the Blackboard copy-paste demo, to be filled in after a test run
