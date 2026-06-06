# StepGPT

A tiny, single-file web app that turns AI-generated step lists into a guided, checkable walkthrough.

Paste in any "10 steps to do X" list an LLM gives you, hit **Create checklist**, and walk through the steps one at a time — marking each **completed**, **skipped**, or leaving it **not attempted**, and jotting notes as you go. Then copy the whole thing back out as clean plain text to feed to your AI.

**Live app:** https://auerlian.github.io/StepGPT/

## How to use it

You can use the live link above, or run it locally — **just open `index.html` in your browser** (double-click it). No install, no server, no internet required.

1. **Paste a list** into the box. Numbered lists, bullets, markdown, or plain lines all work. Lines under a step (indented or continuation text) become that step's details.
2. **Create checklist** — it splits the text into steps.
3. **Walk through** each step: **Mark complete** or **Skip** it, add notes, and use **Previous / Next** (or the ← → arrow keys) to move.
4. **Jump around** with the numbered overview strip at the bottom.
5. **Copy for AI** (top right) copies the list as plain text with every step's status and notes, ready to paste back into an AI agent.
6. Past lists live in the **left sidebar** with live progress. Click to reopen, rename via the title, or delete.

### What "Copy for AI" produces

```
Ship a new feature branch
Progress: 2/6 completed, 1 skipped, 3 not attempted

1. [Completed] Pull the latest main and create a feature branch
   Run: git checkout main && git pull, then git checkout -b feature/my-thing
2. [Skipped] Make your code changes and write tests
   Notes: Skipping — covered by existing CI pipeline.
3. [Completed] Run the full test suite locally and confirm it passes
   Notes: Ran npm test locally, 142 passing.
4. [Not attempted] Commit with a clear message and push the branch
...
```

## Good to know

- **Everything saves automatically** in your browser (localStorage) — close the tab and your lists, statuses, and notes are still there.
- Data is tied to the browser on the machine where you use it. Use **Export** (sidebar) to download a JSON backup, and **Import** to restore it or move it elsewhere.
- Works offline and respects your system light/dark theme.

## Shortcuts

- **⌘/Ctrl + Enter** in the paste box — create the checklist
- **← / →** — previous / next step
- **⌘/Ctrl + Enter** in a notes box — save and go to the next step

## Files

- `index.html` — the entire app (HTML, CSS, and JavaScript in one file)
- `.claude/launch.json` — optional config for previewing via a local dev server
