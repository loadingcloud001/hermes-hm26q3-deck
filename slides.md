---
theme: default
title: 'Hermes Agent — Install & Use'
info: |
  ## Hermes Agent — Install & Use
  A step-by-step walkthrough for new users
  Ref: HM26Q3 · v2
  Presented by: Charles Lo · 2026-07
drawings:
  persist: false
transition: slide-left
mdc: true
---

<div style="position: absolute; inset: 0; background: #FF6B35; color: white; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 60px 80px; text-align: center;">

<div style="font-size: 13px; font-weight: 600; letter-spacing: 4px; opacity: 0.85; margin-bottom: 32px;">
  H M 2 6 Q 3  ·  2 0 2 6 - Q 3
</div>

<h1 style="font-size: 56px; font-weight: 700; color: white; line-height: 1.15; margin: 0 0 18px; letter-spacing: -1px;">
  Hermes Agent<br>Install &amp; Use
</h1>

<div style="font-size: 22px; font-weight: 400; color: white; opacity: 0.95; margin-bottom: 40px;">
  From <code style="background: rgba(255,255,255,0.18); color: white; padding: 2px 9px; border-radius: 5px; font-size: 20px; font-family: 'JetBrains Mono', monospace;">Download</code> to a working bot on Telegram
</div>

<div style="font-size: 14px; color: white; opacity: 0.85; margin-bottom: 56px;">
  Charles Lo · 2026-07 · Windows desktop edition
</div>

<a href="#" target="_blank" style="display: inline-block; padding: 12px 32px; border: 1.5px solid white; color: white; border-radius: 999px; font-size: 13px; font-weight: 600; letter-spacing: 2.5px; text-decoration: none; text-transform: uppercase;">PRESS SPACE →</a>

</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-AGD-001 · v2</div>

# Agenda

<div class="grid grid-cols-3 gap-5" style="margin-top: 36px;">
  <div class="cl-card">
    <div class="cl-letter-badge">a</div>
    <h3 style="margin: 14px 0 8px; font-size: 18px; font-weight: 700; color: #2C2C2C; line-height: 1.3;">Install on Windows</h3>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Download the Hermes Desktop installer. Run it. Done — chat app, model picker, and skills all ready.
    </div>
  </div>
  <div class="cl-card">
    <div class="cl-letter-badge">b</div>
    <h3 style="margin: 14px 0 8px; font-size: 18px; font-weight: 700; color: #2C2C2C; line-height: 1.3;">Choose a provider</h3>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Three setup modes. OpenRouter is fastest — one key covers 200+ models.
    </div>
  </div>
  <div class="cl-card">
    <div class="cl-letter-badge">c</div>
    <h3 style="margin: 14px 0 8px; font-size: 18px; font-weight: 700; color: #2C2C2C; line-height: 1.3;">First conversation</h3>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Open Hermes Desktop, type a real prompt in the chat box, watch the agent work. Three starter prompts included.
    </div>
  </div>
  <div class="cl-card">
    <div class="cl-letter-badge">d</div>
    <h3 style="margin: 14px 0 8px; font-size: 18px; font-weight: 700; color: #2C2C2C; line-height: 1.3;">Verify &amp; key features</h3>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Make sure <code>hermes --continue</code> works. Then: slash commands, multi-line, interrupt.
    </div>
  </div>
  <div class="cl-card">
    <div class="cl-letter-badge">e</div>
    <h3 style="margin: 14px 0 8px; font-size: 18px; font-weight: 700; color: #2C2C2C; line-height: 1.3;">Next layer &amp; Q&amp;A</h3>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Bots, skills, MCP, voice — and the failure modes + recovery toolkit that fix the rest.
    </div>
  </div>
</div>

<div class="cl-footer-meta">21 slides · ~15 minutes · Windows desktop edition</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-WHY-001 · v1</div>

# What you'll get

One installer, three things running on your Windows machine.

<div class="grid grid-cols-2 gap-6" style="margin-top: 28px;">

  <div>
    <div class="cl-eyebrow" style="margin-bottom: 12px;">Installed by the installer</div>
    <div class="cl-desc-box" style="margin-bottom: 14px;">
      <strong style="color: #2C2C2C;">hermes</strong> — the desktop chat app. Native Windows window, no terminal required.
    </div>
    <div class="cl-desc-box" style="margin-bottom: 14px;">
      <strong style="color: #2C2C2C;">hermes-cli</strong> — command-line entry point, on your PATH. Used by the desktop app and by scripts; you don't have to invoke it manually.
    </div>
    <div class="cl-desc-box">
      <strong style="color: #2C2C2C;">Default skills</strong> — installed to <code>%LOCALAPPDATA%\hermes\skills\</code>. Ready to use, no extra setup.
    </div>
  </div>

  <div>
    <div class="cl-eyebrow-purple" style="margin-bottom: 12px;">You can do, on day one</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; padding: 12px 14px; background: var(--card-peach); border-left: 3px solid var(--accent-orange); border-radius: 8px; margin-bottom: 10px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13px; color: #3A3A3A; line-height: 1.5;"><strong style="color: #2C2C2C;">Chat in a window.</strong> Type a request, get a real answer with tool calls. Files, terminal, web search — all from inside the app.</div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; padding: 12px 14px; background: var(--card-peach); border-left: 3px solid var(--accent-orange); border-radius: 8px; margin-bottom: 10px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13px; color: #3A3A3A; line-height: 1.5;"><strong style="color: #2C2C2C;">Pick your model.</strong> OpenRouter routes to Claude, GPT, Gemini, Llama, DeepSeek, Mistral — switch from the model picker, no restart.</div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; padding: 12px 14px; background: var(--card-peach); border-left: 3px solid var(--accent-orange); border-radius: 8px; margin-bottom: 10px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13px; color: #3A3A3A; line-height: 1.5;"><strong style="color: #2C2C2C;">Use skills.</strong> <code>/k8s</code>, <code>/git</code>, <code>/pdf</code> — type <code>/</code> in the chat box for the full list.</div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; padding: 12px 14px; background: var(--card-peach); border-left: 3px solid var(--accent-orange); border-radius: 8px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13px; color: #3A3A3A; line-height: 1.5;"><strong style="color: #2C2C2C;">Stay in flow.</strong> Voice mode (Ctrl+B), session resume, and the gateway for Telegram/Discord/Slack — all toggleable from the menu.</div>
    </div>
  </div>

</div>

<div class="cl-footer-meta">Designed for Windows 10/11 · x64 · ARM64 also supported</div>

---
layout: default
---

<div style="position: absolute; inset: 0; background: #FF6B35; color: white; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 60px 80px; text-align: center;">

<div style="font-size: 13px; font-weight: 600; letter-spacing: 4px; opacity: 0.85; margin-bottom: 28px;">
  S E C T I O N  ·  0 1
</div>

<h1 style="font-size: 64px; font-weight: 700; color: white; line-height: 1.1; margin: 0 0 20px; letter-spacing: -1.5px;">
  Install
</h1>

<div style="font-size: 22px; font-weight: 400; color: white; opacity: 0.95; max-width: 600px; line-height: 1.4;">
  One installer. One click.<br>Everything wired up.
</div>

<div style="position: absolute; bottom: 32px; left: 50px; font-size: 12px; color: white; opacity: 0.7; letter-spacing: 1px;">
  HM26Q3-SEC-01
</div>

</div>

---
layout: default

# ===== NEW INSTALL SECTION — uses real screenshots from user's recording =====

---

<div class="cl-ref-id">HM26Q3-INS-01 · v1</div>

# Step 1 of 4 — Visit the official blue homepage

Open Edge or Chrome and go to the <strong style="color:#FF6B35;">official blue homepage</strong>: <a href="https://hermes-agent.nousresearch.com" target="_blank" style="font-weight:700;color:#FF6B35;">hermes-agent.nousresearch.com</a>. On this blue page you will see three platform cards. Click the <strong style="color:#FF6B35;">Windows</strong> card's <strong style="color:#FF6B35;">DOWNLOAD</strong> button.

<div class="grid grid-cols-5 gap-5" style="margin-top: 18px;">
  <div style="grid-column: span 3; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; box-shadow: 0 4px 16px rgba(0,0,0,0.08); position: relative;">
    <img src="/install-steps/01-download-page.png" style="display: block; width: 100%; height: auto;" />
    <!-- Annotation arrow pointing at the Windows download button -->
    <div style="position: absolute; top: 18%; left: 52%; transform: translate(-50%, -50%); pointer-events: none; z-index: 10;">
      <div style="background: #FF6B35; color: white; padding: 6px 14px; border-radius: 9999px; font-size: 13px; font-weight: 700; box-shadow: 0 3px 12px rgba(255,107,53,0.45); white-space: nowrap;">
        ⬇ Click this Download button
      </div>
      <div style="width: 0; height: 0; border-left: 8px solid transparent; border-right: 8px solid transparent; border-top: 10px solid #FF6B35; margin: 2px auto 0;"></div>
    </div>
  </div>
  <div style="grid-column: span 2;">
    <div class="cl-eyebrow" style="margin-bottom: 10px;">Pick your platform</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Open <strong style="color: #2C2C2C;">Edge</strong> and visit <a href="https://hermes-agent.nousresearch.com" target="_blank" style="color: #FF6B35; font-weight: 600;">hermes-agent.nousresearch.com</a>.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Three download cards appear: <strong style="color: #2C2C2C;">macOS</strong>, <strong style="color: #FF6B35;">Windows</strong>, <strong style="color: #2C2C2C;">Linux</strong>. Click <strong style="color: #FF6B35;">DOWNLOAD</strong> under Windows.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Browser saves <code>Hermes-Setup.exe</code> to <strong style="color: #2C2C2C;">Downloads</strong>. ~240 MB.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Or scroll down — there's an <strong style="color: #2C2C2C;">INSTALL FROM TERMINAL</strong> section with curl / iex commands if you prefer CLI.
      </div>
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 1 of 4 · real recording frame · next: run the installer</div>

---

<div class="cl-ref-id">HM26Q3-INS-02 · v1</div>

# Step 2 of 4 — Run the installer

Double-click <code>Hermes-Setup.exe</code> from your browser downloads. A 16-step installer dialog opens — let it run unattended.

<div class="grid grid-cols-5 gap-5" style="margin-top: 18px;">
  <div style="grid-column: span 3; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; box-shadow: 0 4px 16px rgba(0,0,0,0.08); display: flex; align-items: center; justify-content: center; min-height: 400px; position: relative;">
    <img src="/install-steps/03-installer-running.png" style="display: block; max-width: 100%; max-height: 480px; height: auto;" />
    <div style="position: absolute; top: 18%; left: 50%; transform: translate(-50%, -50%); pointer-events: none; z-index: 10;">
      <div style="background: #FF6B35; color: white; padding: 5px 12px; border-radius: 9999px; font-size: 12px; font-weight: 700; box-shadow: 0 2px 10px rgba(255,107,53,0.5); white-space: nowrap;">
        ⏳ Let it reach 100%
      </div>
      <div style="width: 0; height: 0; border-left: 7px solid transparent; border-right: 7px solid transparent; border-top: 9px solid #FF6B35; margin: 2px auto 0;"></div>
    </div>
  </div>
  <div style="grid-column: span 2;">
    <div class="cl-eyebrow" style="margin-bottom: 10px;">What the installer does</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Opens a window titled <strong style="color: #2C2C2C;">Hermes</strong> with 16 steps: Installing uv package manager · Verifying Python 3.11 · Installing Git · Detecting Node.js · Installing ripgrep and ffmpeg · Cloning Hermes repository · Creating Python virtual environment · Installing Python dependencies · Installing Node.js dependencies · Building desktop app · Adding Hermes to PATH · Writing configuration templates.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Each step shows timing — e.g. <em>Verifying Python 3.11 · 957ms</em>. Total ~1–3 min.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        <strong style="color: #2C2C2C;">Don't close it.</strong> The desktop app needs PATH entries, Start menu link, and the <code>~/.hermes/</code> config dir.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        On completion, a <strong style="color: #FF6B35;">Finish</strong> screen appears — click it to launch Hermes Desktop.
      </div>
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 2 of 4 · real recording frame · next: Hermes Desktop launches</div>

---

<div class="cl-ref-id">HM26Q3-INS-03 · v1</div>

# Step 3 of 4 — Hermes Desktop launches

The installer finishes, the desktop app opens full-screen. If a "Sign in with Nous Portal" dialog appears, **close it** — we will use OpenRouter directly in the next section.

<div class="grid grid-cols-5 gap-5" style="margin-top: 18px;">
  <div style="grid-column: span 3; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
    <img src="/install-steps/05-hermes-desktop-launched.png" style="display: block; width: 100%; height: auto; border-radius: 10px;" />
  </div>
  <div style="grid-column: span 2;">
    <div class="cl-eyebrow" style="margin-bottom: 10px;">Skip the welcome dialog</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Hermes Desktop opens full-screen. If a sign-in dialog appears, click <strong style="color: #FF6B35;">Close</strong> — we will set up the model in the next section.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        The left sidebar shows <em>New chat · MCP · Files · API Token · Auto-Login</em>. The model picker at bottom-right reads <em>OpenRouter</em>.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Status bar at the bottom shows <strong style="color: #2C2C2C;">Gateway ready · Agents · Cron</strong> when the desktop app has finished loading.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Hermes Desktop is now ready. Next: add your OpenRouter API key.
      </div>
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 3 of 4 · real recording frame · next: set up OpenRouter</div>
---

<div class="cl-ref-id">HM26Q3-SET-02 · v1</div>

# Step 2 of 3 — Create an API key

OpenRouter gives you one key that works across every model. No per-vendor credentials.

<div class="grid grid-cols-5 gap-5" style="margin-top: 18px;">
  <div style="grid-column: span 3; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
    <img src="/setup-steps/05-openrouter-keys-page.png" style="display: block; width: 100%; height: auto; border-radius: 10px;" />
  </div>
  <div style="grid-column: span 2;">
    <div class="cl-eyebrow" style="margin-bottom: 10px;">From your dashboard</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Click your avatar → <strong style="color: #FF6B35;">Keys</strong> (or go to <a href="https://openrouter.ai/settings/keys" target="_blank" style="color: #FF6B35; font-weight: 600;">openrouter.ai/settings/keys</a>).
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Click <strong style="color: #FF6B35;">+ New Key</strong>. Give it a name (e.g. <em>Hermes Desktop</em>).
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Copy the key — it starts with <code style="font-size: 12px;">sk-or-v1-…</code>. You will <strong style="color: #2C2C2C;">only see it once</strong>.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Set a spending limit if you like — <em>Keys → click the key → Limit</em>. Default is $0 (free models only).
      </div>
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 2 of 3 · real recording frame · next: add it to Hermes</div>

---

<div class="cl-ref-id">HM26Q3-SET-03 · v1</div>

# Step 3 of 3 — Add the key to Hermes Desktop

Back in the desktop app, open Settings, paste the key, pick a model. Done.

<div class="grid grid-cols-5 gap-5" style="margin-top: 18px;">
  <div style="grid-column: span 3; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
    <img src="/setup-steps/07-config-set-page.png" style="display: block; width: 100%; height: auto; border-radius: 10px;" />
  </div>
  <div style="grid-column: span 2;">
    <div class="cl-eyebrow" style="margin-bottom: 10px;">Wiring up OpenRouter</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        In Hermes Desktop, open <strong style="color: #FF6B35;">Settings → API Keys</strong> (left sidebar).
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Paste your <code style="font-size: 12px;">sk-or-v1-…</code> key into the <strong style="color: #2C2C2C;">OpenRouter</strong> field. Click <strong style="color: #FF6B35;">Save</strong>.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        In the <strong style="color: #2C2C2C;">Model</strong> dropdown, pick: <code style="font-size: 12px;">openrouter/meta-llama/llama-3.3-70b-instruct:free</code> (or any <code style="font-size: 12px;">:free</code> model).
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Status bar shows <strong style="color: #2C2C2C;">Gateway ready</strong> when the key validates. Now type a prompt in the chat box.
      </div>
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 3 of 3 · real recording frame · next: first conversation</div>

---

<div class="cl-ref-id">HM26Q3-CONV-01 · v1</div>

# Type the prompt

Type at the bottom of the chat box. Hit Enter. The agent takes it from there — installing tools, reading files, generating output.

<div class="grid grid-cols-5 gap-5" style="margin-top: 18px;">
  <div style="grid-column: span 3; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; overflow: hidden; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
    <img src="/conversation-steps/01-prompt-typed.png" style="display: block; width: 100%; height: auto;" />
  </div>
  <div style="grid-column: span 2;">
    <div class="cl-eyebrow" style="margin-bottom: 10px;">What you're seeing</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Chat box at the top: <em>"Use this pdf to create 1 nos powerpoint slide to introduce the smart watch."</em>
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Sidebar left: pinned <strong style="color: #2C2C2C;">Use this pdf to create 1 nos...</strong> session. Earlier sessions visible above.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        First tool run: <em>Running code</em> <code style="font-size: 12px;">import subprocess, sys, path = r'C:\Users\TCL13\Downloads\InforSMART_Performan…</code>
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Thinking: <em>"Need to install PDF extraction and check Node/pptxgenjs. Let me set those up."</em>
      </div>
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 8 of 8 · real recording frame · next: agent installs tools</div>

---

<div class="cl-ref-id">HM26Q3-CONV-02 · v1</div>

# Agent installs missing tools

The agent self-installs what it needs: <code>pymupdf</code> for PDF, <code>pptxgenjs</code> + <code>react</code> for the slide. You watch, it works.

<div class="grid grid-cols-5 gap-5" style="margin-top: 18px;">
  <div style="grid-column: span 3; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; overflow: hidden; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
    <img src="/conversation-steps/02-pptxgenjs-install.png" style="display: block; width: 100%; height: auto;" />
  </div>
  <div style="grid-column: span 2;">
    <div class="cl-eyebrow" style="margin-bottom: 10px;">What the agent did</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Read the PDF: <em>"PAGES: ", doc.page_count</em> — 4 pages, each with title + body text printed.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Installed <code style="font-size: 12px;">pptxgenjs</code> via npm (3.0s) — the JS PowerPoint library.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Installed <code style="font-size: 12px;">react react-dom react-icons sharp</code> (5.4s) — for a richer-looking slide with vector icons.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Thinking: <em>"Got the full content. Now I'll build one polished slide. Let me install icon tooling for a richer look, then generate."</em>
      </div>
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 9 of 9 · real recording frame · next: write the slide script</div>

---

<div class="cl-ref-id">HM26Q3-CONV-03 · v1</div>

# Write the slide script

The agent generates <code>extract_pdf.py</code>, a pptxgenjs script, then converts PPTX → PNG via <code>soffice --headless</code>. Two sub-steps, one tool run.

<div class="grid grid-cols-5 gap-5" style="margin-top: 18px;">
  <div style="grid-column: span 3; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; overflow: hidden; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
    <img src="/conversation-steps/03-pptx-script.png" style="display: block; width: 100%; height: auto;" />
  </div>
  <div style="grid-column: span 2;">
    <div class="cl-eyebrow" style="margin-bottom: 10px;">The agent's pipeline</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Wrote <code style="font-size: 12px;">extract_pdf.py</code> — uses pymupdf to dump each page's title + body (1.4s).
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Wrote <code style="font-size: 12px;">slide.js</code> with pptxgenjs — picks an icon for each feature (GPS · Body Temp · G-sensor · Notification · SOS), builds the layout.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Rendered PPTX → PNG via LibreOffice headless (3.2s).
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Thinking: <em>"Let me assign"</em> — assigning each icon to the 5 features on the slide.
      </div>
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 10 of 10 · real recording frame · next: subagent QA</div>

---

<div class="cl-ref-id">HM26Q3-CONV-04 · v1</div>

# Subagent QA

The agent delegates visual inspection to a <strong style="color: #FF6B35;">subagent</strong> (badge top-left: <em>1 Subagent</em>). It checks the rendered PNG against the PDF and confirms the slide looks right.

<div class="grid grid-cols-5 gap-5" style="margin-top: 18px;">
  <div style="grid-column: span 3; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; overflow: hidden; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
    <img src="/conversation-steps/04-subagent-qa.png" style="display: block; width: 100%; height: auto;" />
  </div>
  <div style="grid-column: span 2;">
    <div class="cl-eyebrow" style="margin-bottom: 10px;">Delegation pattern</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        The agent spawns a subagent to read the rendered PNG and verify icon-text alignment, font sizing, contrast.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Top-left badge: <strong style="color: #FF6B35;">1 Subagent</strong> — Hermes Agent's parallel-agent capability.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Status bar: <em>Running 3:02 · Session 3:04</em>. Bottom-right: <em>v0.18.2.98cadad</em>.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        If the subagent finds issues, it tells the main agent — the slide gets refined and re-rendered.
      </div>
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 11 of 11 · real recording frame · next: final result</div>

---

<div class="cl-ref-id">HM26Q3-CONV-05 · v1</div>

# Final result — the slide is ready

The agent delivers the final PowerPoint slide: <strong style="color: #FF6B35;">SMART WATCH 4G — IP67 Intrinsically Safe</strong>, with feature icons (GPS · Body Temp · G-sensor · Notification · SOS) and the product spec table.

<div class="grid grid-cols-5 gap-5" style="margin-top: 18px;">
  <div style="grid-column: span 3; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; overflow: hidden; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
    <img src="/conversation-steps/05-final-slide.png" style="display: block; width: 100%; height: auto;" />
  </div>
  <div style="grid-column: span 2;">
    <div class="cl-eyebrow" style="margin-bottom: 10px;">What's on the slide</div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Hero: <strong style="color: #FF6B35;">SMART WATCH 4G</strong> with the <em>IP67 Intrinsically Safe</em> safety badge.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        5 feature icons: <strong style="color: #2C2C2C;">GPS · Body Temp · G-sensor · Notification · SOS</strong> — each with an icon + short label.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px; margin-bottom: 12px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Spec table on the right with the full product specs.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 12px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.5; padding-top: 2px;">
        Output saved as <code style="font-size: 12px;">InforSMART_…smart_watch_slide.pptx</code>. Download link in the chat.
      </div>
    </div>
  </div>
</div>

<div class="cl-footer-meta">End of demo · real recording · thank you</div>

---

<div class="cl-ref-id">HM26Q3-END-001 · v1</div>

# Q&A

You watched the entire end-to-end flow on Windows: install Hermes Desktop, set up OpenRouter, and watch the agent build a real PowerPoint slide from a PDF — in under 30 minutes of recording.

<div style="margin-top: 30px; padding: 24px 28px; background: #FFE9DA; border-left: 4px solid #FF6B35; border-radius: 8px;">
  <h3 style="margin: 0 0 8px; font-size: 17px; color: #FF6B35;">Where to go next</h3>
  <ul style="margin: 0; padding-left: 18px; font-size: 14px; line-height: 1.7; color: #2C2C2C;">
    <li><a href="https://hermes-agent.nousresearch.com/docs" target="_blank" style="color: #FF6B35; font-weight: 600;">Full docs</a> · every command, every provider, every MCP server</li>
    <li><a href="https://openrouter.ai/models" target="_blank" style="color: #FF6B35; font-weight: 600;">AI Providers</a> · 30+ providers including OpenRouter, Anthropic, Google, GitHub Copilot</li>
    <li><a href="https://hermes-agent.nousresearch.com/docs/user-guide/features/skills" target="_blank" style="color: #FF6B35; font-weight: 600;">Skills System</a> · reusable workflows like the PowerPoint one we just used</li>
    <li><a href="https://hermes-agent.nousresearch.com/docs/user-guide/messaging/" target="_blank" style="color: #FF6B35; font-weight: 600;">Messaging Gateway</a> · Telegram, Discord, Slack, WhatsApp, Signal, Email, Teams</li>
    <li><a href="https://hermes-agent.nousresearch.com/docs/getting-started/quickstart" target="_blank" style="color: #FF6B35; font-weight: 600;">Quickstart</a> · the full text version of what we covered</li>
  </ul>
</div>

<div class="cl-footer-meta">19 slides · recorded live on Windows · Charles Lo · 2026-07</div>
