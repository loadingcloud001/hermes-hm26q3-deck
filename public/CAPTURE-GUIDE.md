# Capturing the install + setup screenshots

These are the frames Hermes Agent's slide deck needs. Take them on a
clean Windows 11 VM (or a freshly-reset PC) so the screenshots show
real, current UI states.

Save each as PNG in the folder named below.

## Install flow — `public/install-steps/`

Capture these 7 frames during a single clean install session.

| File | What to capture | When |
|---|---|---|
| `01-download-page.png` | Edge/Chrome showing `hermes-agent.nousresearch.com` with the orange "Download for Windows" button visible | After loading the homepage |
| `02-smartscreen.png` | Windows SmartScreen "Windows protected your PC" dialog with the "More info" link visible | Immediately after double-clicking the .exe |
| `03-smartscreen-expanded.png` | Same dialog AFTER clicking "More info" — the "Run anyway" button is now visible | Right after expanding |
| `04-uac.png` | User Account Control dialog "Do you want to allow this app to make changes to your device?" with publisher = Nous Research | After SmartScreen passed |
| `05-progress.png` | Installer window at ~60% complete, status list visible (Python, Node.js, ripgrep done; cloning in progress) | Mid-install |
| `06-finish.png` | Finish screen "Setup was completed successfully" with "Launch Hermes Desktop" checkbox pre-checked | At 100% |
| `07-desktop-launching.png` | Hermes Desktop window opening (the welcome / first-run wizard if any) | Immediately after clicking Finish |

## First-time setup flow — `public/setup-steps/`

Capture these 5 frames during the first launch.

| File | What to capture |
|---|---|
| `01-welcome.png` | The setup wizard first screen — "Welcome to Hermes Agent" |
| `02-mode-picker.png` | The three setup modes (Quick Setup · Nous Portal / Full Setup / Blank Slate) |
| `03-portal-login.png` | The browser opening to Nous Portal OAuth login |
| `04-model-picker.png` | The chat window after setup completes, showing the model picker |
| `05-first-chat.png` | A successful first chat — your real prompt, the agent's reply, the tool-call banner |

## First conversation flow — `public/conversation-steps/`

Capture these 3 frames showing the chat working.

| File | What to capture |
|---|---|
| `01-prompt-typed.png` | A starter prompt typed in the chat box (e.g. "Summarise this repo in 5 bullets") before pressing Enter |
| `02-tool-running.png` | The agent mid-tool-call (file read / terminal / web search) with the tool badge visible |
| `03-final-response.png` | The completed answer in the chat window |

## Failure modes — `public/failure-modes/`

For the recovery slide: take a screenshot of each error you hit, or
mock them as text mocks if you can't easily reproduce them. The
frames go into the failure-modes table.

## Tips

- **1080p (1920×1080)** is the sweet spot — large enough to read
  on a projector, small enough not to bloat the bundle.
- Crop the screenshots to just the relevant window (use the
  Snipping Tool — `Win + Shift + S`).
- Use PNG, not JPG, so text stays sharp.
- If a dialog has long text that wraps, capture the whole window
  — don't crop mid-dialog.
- Add an audio commentary track if you want — the deck can show
  captions later.

When you're done, drop all PNGs into this folder and tell me. I'll
plug them into the slide shell and we'll deploy together.