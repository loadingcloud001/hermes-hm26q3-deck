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
      Three setup modes. Nous Portal is fastest — one login covers 300+ models.
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
      <div style="font-size: 13px; color: #3A3A3A; line-height: 1.5;"><strong style="color: #2C2C2C;">Pick your model.</strong> Nous Portal, Claude, GPT, Gemini, DeepSeek, GitHub Copilot — switch from the model picker, no restart.</div>
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
---

<div class="cl-ref-id">HM26Q3-INS-01 · v1</div>

# Step 1 of 6 — Download the installer

Go to <code>hermes-agent.nousresearch.com</code> in your browser. Click the orange <strong style="color: #2C2C2C;">Download for Windows</strong> button.

<div class="grid grid-cols-2 gap-8" style="margin-top: 18px; align-items: stretch;">

  <!-- LEFT: the website mock -->
  <div>
    <div style="background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; overflow: hidden; box-shadow: 0 6px 20px rgba(0,0,0,0.06);">
      <!-- fake browser chrome -->
      <div style="background: #F4F4F4; padding: 8px 12px; display: flex; align-items: center; gap: 8px; border-bottom: 1px solid #E5E5E5;">
        <span style="width: 10px; height: 10px; border-radius: 50%; background: #FF5F57;"></span>
        <span style="width: 10px; height: 10px; border-radius: 50%; background: #FEBC2E;"></span>
        <span style="width: 10px; height: 10px; border-radius: 50%; background: #28C840;"></span>
        <div style="flex: 1; background: white; border-radius: 5px; padding: 4px 10px; font-size: 11px; color: #555; font-family: 'JetBrains Mono', monospace; margin-left: 8px;">
          🔒 https://hermes-agent.nousresearch.com
        </div>
      </div>
      <!-- page header -->
      <div style="padding: 14px 18px; border-bottom: 1px solid #F0F0F0; display: flex; align-items: center; justify-content: space-between;">
        <div style="display: flex; align-items: center; gap: 8px;">
          <span style="display: inline-block; width: 22px; height: 22px; background: #FF6B35; border-radius: 6px;"></span>
          <span style="font-weight: 700; font-size: 14px; color: #2C2C2C;">Hermes Agent</span>
        </div>
        <div style="font-size: 11px; color: #888;">
          <a href="https://hermes-agent.nousresearch.com/docs" target="_blank" style="color: #888; text-decoration: none;">Docs</a> · <a href="https://github.com/hermes-agent" target="_blank" style="color: #888; text-decoration: none;">GitHub</a> · <a href="https://discord.gg/hermes-agent" target="_blank" style="color: #888; text-decoration: none;">Discord</a>
        </div>
      </div>
      <!-- page body -->
      <div style="padding: 32px 24px; text-align: center;">
        <div style="font-size: 11px; color: #888; letter-spacing: 2px; text-transform: uppercase; margin-bottom: 10px;">W I N D O W S  ·  D E S K T O P</div>
        <div style="font-size: 22px; font-weight: 700; color: #2C2C2C; line-height: 1.2; margin-bottom: 18px;">Your AI agent,<br>on your machine.</div>
        <a href="https://hermes-agent.nousresearch.com/download" target="_blank" style="display: inline-block; background: #FF6B35; color: white; padding: 10px 22px; border-radius: 8px; font-size: 13px; font-weight: 600; box-shadow: 0 4px 12px rgba(255,107,53,0.35); text-decoration: none;">
          ⬇ Download for Windows
        </a>
        <div style="font-size: 10px; color: #888; margin-top: 10px;">Hermes-Desktop-Setup.exe · ~240 MB · Windows 10 / 11</div>
      </div>
    </div>
    <div style="text-align: center; font-size: 11px; color: #999; margin-top: 8px; font-style: italic;">Mock-up of <a href="https://hermes-agent.nousresearch.com" target="_blank" style="color: #FF6B35; text-decoration: none;">hermes-agent.nousresearch.com</a></div>
  </div>

  <!-- RIGHT: numbered instructions -->
  <div>
    <div style="display: flex; align-items: flex-start; gap: 14px; margin-bottom: 18px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 14px; color: #3A3A3A; line-height: 1.55; padding-top: 2px;">
        Open <strong style="color: #2C2C2C;">Edge</strong> or <strong style="color: #2C2C2C;">Chrome</strong> and visit:
        <a href="https://hermes-agent.nousresearch.com" target="_blank" style="display: block; background: #1E1E1E; color: #FF8C42; border-radius: 6px; padding: 8px 12px; font-family: 'JetBrains Mono', monospace; font-size: 13px; margin-top: 8px; text-decoration: none; word-break: break-all;">
          ↗ https://hermes-agent.nousresearch.com
        </a>
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 14px; margin-bottom: 18px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 14px; color: #3A3A3A; line-height: 1.55; padding-top: 2px;">
        Click the orange <strong style="color: #FF6B35;">Download for Windows</strong> button. Your browser saves <code>Hermes-Desktop-Setup.exe</code> to <strong style="color: #2C2C2C;">Downloads</strong>.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 14px; margin-bottom: 18px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 14px; color: #3A3A3A; line-height: 1.55; padding-top: 2px;">
        Wait for the download to finish. The file is roughly <strong style="color: #2C2C2C;">240 MB</strong> — usually under 90 seconds on a home network.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 14px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 14px; color: #3A3A3A; line-height: 1.55; padding-top: 2px;">
        When the download bar completes, leave the browser open for now — <strong style="color: #2C2C2C;">Step 2</strong> opens the file you just saved.
      </div>
    </div>
    <div style="margin-top: 18px; padding: 12px 14px; background: rgba(124, 58, 237, 0.06); border-left: 3px solid #7C3AED; border-radius: 6px; font-size: 12.5px; color: #4A4A4A;">
      <strong style="color: #7C3AED;">Don't have admin rights?</strong> Ask your IT team to install it for you. The installer writes to <code>%LOCALAPPDATA%</code> (no UAC), but the first run registers a Start menu entry that may need admin.
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 1 of 6 · next: open the installer · full guide: <a href="https://hermes-agent.nousresearch.com/docs/getting-started/installation" target="_blank" style="color: #888; text-decoration: none;">installation</a></div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-INS-02 · v1</div>

# Step 2 of 6 — Open the installer

Find <code>Hermes-Desktop-Setup.exe</code> in your <strong style="color: #2C2C2C;">Downloads</strong> folder and double-click it.

<div class="grid grid-cols-2 gap-8" style="margin-top: 18px; align-items: stretch;">

  <!-- LEFT: Windows SmartScreen mock -->
  <div>
    <div style="background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; overflow: hidden; box-shadow: 0 8px 24px rgba(0,0,0,0.10);">
      <!-- title bar -->
      <div style="background: #F4F4F4; padding: 8px 12px; border-bottom: 1px solid #E5E5E5; font-size: 11px; color: #666;">
        Microsoft Defender SmartScreen
      </div>
      <!-- dialog body -->
      <div style="padding: 28px 28px 22px;">
        <!-- blue shield -->
        <div style="display: flex; align-items: center; gap: 14px; margin-bottom: 16px;">
          <div style="width: 36px; height: 36px; border-radius: 50%; background: #2D7DD2; display: flex; align-items: center; justify-content: center; color: white; font-size: 18px; font-weight: 700;">ⓘ</div>
          <div>
            <div style="font-size: 15px; font-weight: 600; color: #2C2C2C;">Windows protected your PC</div>
            <div style="font-size: 12px; color: #666; margin-top: 2px;">Microsoft Defender SmartScreen prevented an unrecognized app from starting</div>
          </div>
        </div>
        <div style="background: #FAFAFA; border: 1px solid #ECECEC; border-radius: 6px; padding: 12px 14px; font-size: 12.5px; color: #4A4A4A; line-height: 1.5; margin-bottom: 16px;">
          Running this app might put your PC at risk. The app is not signed by a publisher we recognize. The publisher is <strong style="color: #2C2C2C;">Nous Research</strong>.
        </div>
        <div style="display: flex; gap: 8px; justify-content: flex-end; margin-bottom: 12px;">
          <span style="padding: 7px 14px; background: #F4F4F4; border: 1px solid #D0D0D0; border-radius: 4px; font-size: 12.5px; color: #2C2C2C;">Don't run</span>
          <span style="padding: 7px 14px; background: #F4F4F4; border: 1px solid #D0D0D0; border-radius: 4px; font-size: 12.5px; color: #2C2C2C;">Run anyway</span>
        </div>
        <div style="padding-top: 12px; border-top: 1px dashed #FF6B35; text-align: center;">
          <div style="display: inline-block; background: #FF6B35; color: white; border-radius: 50%; width: 22px; height: 22px; line-height: 22px; font-size: 12px; font-weight: 700; margin-right: 6px;">1</div>
          <span style="font-size: 12px; color: #2C2C2C; font-weight: 600;">Click here first — <em style="color: #FF6B35;">"More info"</em> expands the dialog</span>
        </div>
      </div>
    </div>
    <div style="text-align: center; font-size: 11px; color: #999; margin-top: 8px; font-style: italic;">Mock-up of the Windows SmartScreen warning</div>
  </div>
  <div>
    <div style="display: flex; align-items: flex-start; gap: 14px; margin-bottom: 16px;">
      <span class="cl-num-badge">1</span>
      <div style="font-size: 14px; color: #3A3A3A; line-height: 1.55; padding-top: 2px;">
        Press <kbd style="background: #F4F4F4; border: 1px solid #D0D0D0; border-radius: 3px; padding: 1px 6px; font-family: 'JetBrains Mono', monospace; font-size: 12px;">Ctrl</kbd> + <kbd style="background: #F4F4F4; border: 1px solid #D0D0D0; border-radius: 3px; padding: 1px 6px; font-family: 'JetBrains Mono', monospace; font-size: 12px;">J</kbd> to open <strong style="color: #2C2C2C;">Downloads</strong> in File Explorer. Or click the download bar at the bottom of your browser.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 14px; margin-bottom: 16px;">
      <span class="cl-num-badge">2</span>
      <div style="font-size: 14px; color: #3A3A3A; line-height: 1.55; padding-top: 2px;">
        <strong style="color: #2C2C2C;">Double-click</strong> <code>Hermes-Desktop-Setup.exe</code>.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 14px; margin-bottom: 16px;">
      <span class="cl-num-badge">3</span>
      <div style="font-size: 14px; color: #3A3A3A; line-height: 1.55; padding-top: 2px;">
        If you see <strong style="color: #2C2C2C;">"Windows protected your PC"</strong> (SmartScreen): click <strong style="color: #FF6B35;">More info</strong>, then click <strong style="color: #FF6B35;">Run anyway</strong>. This is normal for new Windows installers from publishers we don't recognise yet.
      </div>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 14px; margin-bottom: 16px;">
      <span class="cl-num-badge">4</span>
      <div style="font-size: 14px; color: #3A3A3A; line-height: 1.55; padding-top: 2px;">
        Next: <strong style="color: #2C2C2C;">approve the UAC prompt</strong> in Step 3.
      </div>
    </div>
    <div style="padding: 12px 14px; background: rgba(255, 107, 53, 0.06); border-left: 3px solid #FF6B35; border-radius: 6px; font-size: 12.5px; color: #4A4A4A;">
      <strong style="color: #FF6B35;">Why this appears:</strong> SmartScreen blocks every .exe it hasn't seen millions of times. Hermes Desktop is new — the warning will disappear once enough people install it.
    </div>
  </div>
</div>

<div class="cl-footer-meta">Step 2 of 6 · next: approve the UAC prompt · troubleshooting: <a href="https://hermes-agent.nousresearch.com/docs/getting-started/installation" target="_blank" style="color: #888; text-decoration: none;">installation guide</a></div>