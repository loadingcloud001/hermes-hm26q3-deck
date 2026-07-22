---
theme: default
title: 'Hermes Agent — Install & First Run'
info: |
  ## Hermes Agent — Install & First Run
  Get Hermes Desktop running on Windows in ~30 minutes.
  Ref: HM26Q3 · v3
  Presented by: Charles Lo · 2026-07
drawings:
  persist: false
transition: slide-left
mdc: true
canvasWidth: 980
aspectRatio: '16/9'
---

<div class="cl-ref-id">HM26Q3-COV-001 · v3</div>

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%); color: white; display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 60px 80px; text-align: center;">

<div style="font-size: 13px; font-weight: 600; letter-spacing: 4px; opacity: 0.9; margin-bottom: 32px;">
  H M 2 6 Q 3  ·  2 0 2 6 - Q 3
</div>

<h1 style="font-size: 56px; font-weight: 700; color: white; line-height: 1.15; margin: 0 0 18px; letter-spacing: -1px;">
  Hermes Agent<br>Install &amp; First Run
</h1>

<div style="font-size: 22px; font-weight: 400; color: white; opacity: 0.95; margin-bottom: 24px; max-width: 720px;">
  Get a working AI agent on your Windows desktop in about 30 minutes — using a free OpenRouter model.
</div>

<div style="font-size: 14px; color: white; opacity: 0.85; margin-bottom: 56px;">
  Charles Lo · 2026-07 · Windows edition
</div>

<a href="#" target="_blank" style="display: inline-block; padding: 12px 32px; border: 1.5px solid white; color: white; border-radius: 999px; font-size: 13px; font-weight: 600; letter-spacing: 2.5px; text-decoration: none; text-transform: uppercase;">PRESS SPACE →</a>

</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-AGD-001 · v3</div>

# Agenda

<div style="font-size: 15px; color: #5A5A5A; margin-top: -8px; margin-bottom: 24px; max-width: 720px;">
  Four short sections. By the end, you'll have Hermes Desktop open, configured against OpenRouter's free tier, and answering your first prompt.
</div>

<div class="grid grid-cols-2 gap-5" style="margin-top: 12px;">
  <div class="cl-card-white">
    <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 10px;">
      <div class="cl-num-badge" style="background: #FF6B35;">1</div>
      <h3 style="margin: 0; font-size: 18px; font-weight: 700; color: #2C2C2C;">Download &amp; Install</h3>
    </div>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Get the official Windows installer from hermes-agent.nousresearch.com, run it, and let it set up Python, uv, Git, and the Hermes desktop app.
    </div>
  </div>
  <div class="cl-card-white">
    <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 10px;">
      <div class="cl-num-badge" style="background: #7C3AED;">2</div>
      <h3 style="margin: 0; font-size: 18px; font-weight: 700; color: #2C2C2C;">Set up OpenRouter</h3>
    </div>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Create an OpenRouter account, generate an API key, point Hermes at it via <code>hermes config</code>. Free tier covers dozens of models.
    </div>
  </div>
  <div class="cl-card-white">
    <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 10px;">
      <div class="cl-num-badge" style="background: #4FA85C;">3</div>
      <h3 style="margin: 0; font-size: 18px; font-weight: 700; color: #2C2C2C;">Pick a free model</h3>
    </div>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Set the default model to something free and reliable: Tencent Hy3 or NVIDIA Nemotron 3. No credit card needed.
    </div>
  </div>
  <div class="cl-card-white">
    <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 10px;">
      <div class="cl-num-badge" style="background: #D0832F;">4</div>
      <h3 style="margin: 0; font-size: 18px; font-weight: 700; color: #2C2C2C;">Your first chat</h3>
    </div>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Launch the desktop app, type a real prompt, watch the agent work. Three starter prompts included.
    </div>
  </div>
</div>

<div style="position: absolute; bottom: 28px; left: 50px; font-size: 11px; color: #999;">
  HM26Q3 · 21 slides · ~30 minutes · Windows desktop
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-WHY-001 · v3</div>

# What you'll have at the end

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 16px; height: 408px;">
  <div style="display: flex; flex-direction: column; gap: 12px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">After 30 minutes</div>
    <h2 style="margin: 0; font-size: 26px; line-height: 1.25;">A real AI agent that lives on your Windows machine</h2>
    <div style="font-size: 14px; color: #3A3A3A; line-height: 1.6; max-width: 480px;">
      Hermes Desktop is a native chat app powered by an LLM you control. It can read files, run shell commands, edit code, install tools, and remember what you told it last session. The model behind it is just a config setting — swap it any time.
    </div>
    <div class="cl-desc-box" style="margin-top: 8px;">
      <strong>What you won't need:</strong> a credit card, a Nous Portal account, or to compile anything from source. Just the installer and one API key.
    </div>
  </div>
  <div style="display: flex; flex-direction: column; gap: 10px; overflow: hidden; min-height: 0;">
    <div class="cl-card-orange-top" style="flex: 1; display: flex; flex-direction: column; justify-content: center;">
      <div style="display: flex; align-items: baseline; gap: 12px;">
        <span style="font-size: 36px; font-weight: 800; color: #FF6B35;">~30</span>
        <span style="font-size: 13px; color: #5A5A5A;">minutes total</span>
      </div>
      <div style="font-size: 11.5px; color: #888; margin-top: 4px;">From cold Windows to first agent reply.</div>
    </div>
    <div class="cl-card-orange-top" style="flex: 1; display: flex; flex-direction: column; justify-content: center;">
      <div style="display: flex; align-items: baseline; gap: 12px;">
        <span style="font-size: 36px; font-weight: 800; color: #FF6B35;">$0</span>
        <span style="font-size: 13px; color: #5A5A5A;">to run</span>
      </div>
      <div style="font-size: 11.5px; color: #888; margin-top: 4px;">OpenRouter free tier + local compute.</div>
    </div>
    <div class="cl-card-orange-top" style="flex: 1; display: flex; flex-direction: column; justify-content: center;">
      <div style="display: flex; align-items: baseline; gap: 12px;">
        <span style="font-size: 36px; font-weight: 800; color: #FF6B35;">20+</span>
        <span style="font-size: 13px; color: #5A5A5A;">models to swap between</span>
      </div>
      <div style="font-size: 11.5px; color: #888; margin-top: 4px;">Change one config line, restart, done.</div>
    </div>
  </div>
</div>

---
layout: section
---

<div class="cl-ref-id">HM26Q3-S1-001 · v3</div>

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%); display: flex; flex-direction: column; align-items: center; justify-content: center; color: white; text-align: center;">

<div style="font-size: 13px; font-weight: 600; letter-spacing: 4px; opacity: 0.85; margin-bottom: 24px;">
  STEP 1 OF 4
</div>

<h1 style="font-size: 64px; font-weight: 800; color: white; margin: 0; letter-spacing: -1.5px; line-height: 1.1;">
  Download &amp; Install
</h1>

<div style="font-size: 20px; color: white; opacity: 0.9; margin-top: 28px; max-width: 620px; line-height: 1.4;">
  Get the official Windows installer and let it set up everything you need.
</div>

</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S1-002 · v3</div>

# Step 1 — Go to the official download page

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 6px; height: 408px; overflow: hidden; grid-template-rows: minmax(0, 1fr);">
  <div style="position: relative; display: flex; flex-direction: column; border: 1px solid #eadfd8; border-radius: 16px; box-shadow: 0 10px 24px rgba(92,68,56,.10); background: #fff; padding: 10px; overflow: hidden; min-height: 0; height: 100%;">
    <div style="position: absolute; top: 14px; left: 14px; z-index: 2;">
      <span class="cl-image-pill">① OFFICIAL SITE</span>
    </div>
    <img src="/images/01-website-hero.png" style="width: 100%; height: 100%; object-fit: contain; background: #0a0a0a; border-radius: 8px;">
  </div>
  <div style="display: flex; flex-direction: column; gap: 12px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">URL to open</div>
    <h2 style="margin: 0; font-size: 22px; line-height: 1.25;">hermes-agent.nousresearch.com</h2>
    <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.6;">
      This is the official Nous Research page for Hermes Agent. The blue <strong>INSTALL</strong> button in the centre takes you to the download links. Click <code>DOWNLOAD FOR WINDOWS</code> and your browser pulls down <code>Hermes-Setup (X).exe</code>.
    </div>
    <div class="cl-desc-box">
      <strong>What you see on the right of this screenshot:</strong> the installer is already running, working through its checklist. You'll get here about 10 seconds after the .exe finishes downloading.
    </div>
    <div style="display: flex; justify-content: space-between; align-items: center; padding: 10px 14px; background: #FFFFFF; border: 1px solid #FF6B35; border-radius: 10px; margin-top: 4px;">
      <span style="font-size: 12px; color: #3A3A3A;">Browser blocked the download? Open it directly:</span>
      <a href="https://hermes-agent.nousresearch.com/" target="_blank" rel="noopener" style="display: inline-block; padding: 7px 14px; background: #FF6B35; color: white; border-radius: 6px; font-size: 11.5px; font-weight: 600; text-decoration: none; letter-spacing: 0.3px;">Open download page ↗</a>
    </div>
    <div style="font-size: 11.5px; color: #888; line-height: 1.5; margin-top: 4px;">
      File size: ~50–80 MB · takes 10–60 seconds on a normal connection.
    </div>
  </div>
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S1-003 · v3</div>

# Run the installer

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 6px; height: 408px; overflow: hidden; grid-template-rows: minmax(0, 1fr);">
  <div style="position: relative; display: flex; flex-direction: column; border: 1px solid #eadfd8; border-radius: 16px; box-shadow: 0 10px 24px rgba(92,68,56,.10); background: #fff; padding: 10px; overflow: hidden; min-height: 0; height: 100%;">
    <div style="position: absolute; top: 14px; left: 14px; z-index: 2;">
      <span class="cl-image-pill">② INSTALLER RUNNING</span>
    </div>
    <img src="/images/02-installer-running.png" style="width: 100%; height: 100%; object-fit: contain; background: #fff; border-radius: 8px;">
  </div>
  <div style="display: flex; flex-direction: column; gap: 12px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">Double-click the .exe</div>
    <h2 style="margin: 0; font-size: 22px; line-height: 1.25;">A guided setup, not a silent installer</h2>
    <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.6;">
      Windows will ask "Do you want to allow this app to make changes?" — click <strong>Yes</strong>. The installer opens a window with a checklist.
    </div>
    <div class="cl-desc-box">
      <strong>What it shows you:</strong> every step it's about to take, in plain English. You can read each line before it runs. No silent registry edits.
    </div>
    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 4px;">
      <div style="background: #FFF8F4; border: 1px solid #FFE3D6; border-radius: 8px; padding: 8px 10px;">
        <div style="font-size: 10px; color: #888; letter-spacing: 1px;">DURATION</div>
        <div style="font-size: 16px; font-weight: 700; color: #FF6B35;">3–5 min</div>
      </div>
      <div style="background: #FFF8F4; border: 1px solid #FFE3D6; border-radius: 8px; padding: 8px 10px;">
        <div style="font-size: 10px; color: #888; letter-spacing: 1px;">REBOOT NEEDED</div>
        <div style="font-size: 16px; font-weight: 700; color: #FF6B35;">No</div>
      </div>
    </div>
  </div>
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S1-004 · v3</div>

# What the installer adds to your machine

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 6px; height: 408px; overflow: hidden; grid-template-rows: minmax(0, 1fr);">
  <div style="position: relative; display: flex; flex-direction: column; border: 1px solid #eadfd8; border-radius: 16px; box-shadow: 0 10px 24px rgba(92,68,56,.10); background: #fff; padding: 10px; overflow: hidden; min-height: 0; height: 100%;">
    <div style="position: absolute; top: 14px; left: 14px; z-index: 2;">
      <span class="cl-image-pill">③ DEPENDENCIES</span>
    </div>
    <img src="/images/03-installer-deps.png" style="width: 100%; height: 100%; object-fit: contain; background: #fff; border-radius: 8px;">
  </div>
  <div style="display: flex; flex-direction: column; gap: 10px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">Five things, one installer</div>
    <h2 style="margin: 0; font-size: 20px; line-height: 1.25;">Python, uv, Git, Node, and the app itself</h2>
    <div style="font-size: 12.5px; color: #3A3A3A; line-height: 1.5;">
      Hermes needs a Python runtime and a few standard developer tools. The installer fetches any you're missing.
    </div>
    <div style="display: flex; flex-direction: column; gap: 6px; margin-top: 4px;">
      <div style="display: flex; align-items: center; gap: 10px; padding: 8px 12px; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 8px;">
        <span style="font-size: 16px; font-weight: 800; color: #FF6B35; width: 22px;">1</span>
        <span style="font-size: 13px; color: #2C2C2C;"><strong>Node.js</strong> — runtime for the desktop shell</span>
      </div>
      <div style="display: flex; align-items: center; gap: 10px; padding: 8px 12px; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 8px;">
        <span style="font-size: 16px; font-weight: 800; color: #FF6B35; width: 22px;">2</span>
        <span style="font-size: 13px; color: #2C2C2C;"><strong>Python 3.11+</strong> — the agent runs on this</span>
      </div>
      <div style="display: flex; align-items: center; gap: 10px; padding: 8px 12px; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 8px;">
        <span style="font-size: 16px; font-weight: 800; color: #FF6B35; width: 22px;">3</span>
        <span style="font-size: 13px; color: #2C2C2C;"><strong>uv</strong> — fast Python package manager</span>
      </div>
      <div style="display: flex; align-items: center; gap: 10px; padding: 8px 12px; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 8px;">
        <span style="font-size: 16px; font-weight: 800; color: #FF6B35; width: 22px;">4</span>
        <span style="font-size: 13px; color: #2C2C2C;"><strong>Git for Windows</strong> — for skills that clone repos</span>
      </div>
      <div style="display: flex; align-items: center; gap: 10px; padding: 8px 12px; background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 8px;">
        <span style="font-size: 16px; font-weight: 800; color: #FF6B35; width: 22px;">5</span>
        <span style="font-size: 13px; color: #2C2C2C;"><strong>Hermes Desktop</strong> — the chat app itself</span>
      </div>
    </div>
  </div>
</div>

---
layout: section
---

<div class="cl-ref-id">HM26Q3-S2-001 · v3</div>

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #7C3AED 0%, #A855F7 100%); display: flex; flex-direction: column; align-items: center; justify-content: center; color: white; text-align: center;">

<div style="font-size: 13px; font-weight: 600; letter-spacing: 4px; opacity: 0.85; margin-bottom: 24px;">
  STEP 2 OF 4
</div>

<h1 style="font-size: 64px; font-weight: 800; color: white; margin: 0; letter-spacing: -1.5px; line-height: 1.1;">
  Set up OpenRouter
</h1>

<div style="font-size: 20px; color: white; opacity: 0.9; margin-top: 28px; max-width: 620px; line-height: 1.4;">
  One account, one API key, 200+ models.
</div>

</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S2-002 · v3</div>

# Why OpenRouter?

<div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; margin-top: 28px;">
  <div class="cl-card-white" style="display: flex; flex-direction: column; gap: 10px">
    <div class="cl-eyebrow">ONE KEY, MANY MODELS</div>
    <h3 style="margin: 0; font-size: 18px; font-weight: 700; color: #2C2C2C;">200+ models, one bill</h3>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      OpenRouter is a unified API that sits in front of every major LLM provider — Anthropic, OpenAI, Google, Meta, Mistral, DeepSeek, and dozens of open-source models. You sign up once, get one key, swap models by changing one string in your config.
    </div>
  </div>
  <div class="cl-card-white" style="display: flex; flex-direction: column; gap: 10px">
    <div class="cl-eyebrow" style="color: #7C3AED;">FREE TIER EXISTS</div>
    <h3 style="margin: 0; font-size: 18px; font-weight: 700; color: #2C2C2C;">Real free models, no card</h3>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Several models stay free all day: Tencent Hy3, NVIDIA Nemotron 3 Super, NVIDIA Nemotron 3 Ultra. No credit card on signup. Rate-limited but enough for personal use.
    </div>
  </div>
  <div class="cl-card-white" style="display: flex; flex-direction: column; gap: 10px">
    <div class="cl-eyebrow" style="color: #4FA85C;">YOU STAY IN CONTROL</div>
    <h3 style="margin: 0; font-size: 18px; font-weight: 700; color: #2C2C2C;">Swap providers any time</h3>
    <div style="font-size: 13px; color: #5A5A5A; line-height: 1.55;">
      Tired of free models? Add a paid key from any other provider later. The model setting is just a string — <code>provider/model-name</code>. No lock-in.
    </div>
  </div>
</div>

<div class="cl-desc-box" style="margin-top: 32px;">
  <strong>What OpenRouter is not:</strong> a model. It's a router. The actual AI runs on someone else's GPU; OpenRouter just relays the request and handles billing.
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S2-003 · v3</div>

# Step 1 — Create your OpenRouter account

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 6px; height: 408px; overflow: hidden; grid-template-rows: minmax(0, 1fr);">
  <div style="position: relative; display: flex; flex-direction: column; border: 1px solid #eadfd8; border-radius: 16px; box-shadow: 0 10px 24px rgba(92,68,56,.10); background: #fff; padding: 10px; overflow: hidden; min-height: 0; height: 100%;">
    <div style="position: absolute; top: 14px; left: 14px; z-index: 2;">
      <span class="cl-image-pill">④ SIGN UP</span>
    </div>
    <img src="/images/04-openrouter-signup.png" style="width: 100%; height: 100%; object-fit: contain; background: #0a0a0a; border-radius: 8px;">
  </div>
  <div style="display: flex; flex-direction: column; gap: 12px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">URL</div>
    <h2 style="margin: 0; font-size: 22px; line-height: 1.25;">openrouter.ai → Sign Up</h2>
    <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.6;">
      Click <strong>Sign Up</strong> in the top-right. You can register with GitHub, Google, or email + password. All three are equivalent for free-tier use.
    </div>
    <div class="cl-desc-box">
      <strong>Watch out for:</strong> the form asks for an email but doesn't require verification to start using the free tier. You can skip the "verify your email" step until later.
    </div>
    <div style="font-size: 11.5px; color: #888; line-height: 1.5; margin-top: 4px;">
      Time: 30 seconds · No credit card · Email-only signup works on mobile too.
    </div>
  </div>
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S2-004 · v3</div>

# Step 2 — Generate an API key

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 6px; height: 408px; overflow: hidden; grid-template-rows: minmax(0, 1fr);">
  <div style="position: relative; display: flex; flex-direction: column; border: 1px solid #eadfd8; border-radius: 16px; box-shadow: 0 10px 24px rgba(92,68,56,.10); background: #fff; padding: 10px; overflow: hidden; min-height: 0; height: 100%;">
    <div style="position: absolute; top: 14px; left: 14px; z-index: 2;">
      <span class="cl-image-pill">⑤ API KEYS</span>
    </div>
    <img src="/images/05-openrouter-keys.png" style="width: 100%; height: 100%; object-fit: contain; background: #0a0a0a; border-radius: 8px;">
  </div>
  <div style="display: flex; flex-direction: column; gap: 12px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">After signing in</div>
    <h2 style="margin: 0; font-size: 22px; line-height: 1.25;">openrouter.ai → Keys</h2>
    <div style="font-size: 13.5px; color: #3A3A3A; line-height: 1.6;">
      Click the <strong>+ New Key</strong> button (top-right of the API Keys page). Give it a memorable name like <code>hermes-laptop</code>. OpenRouter generates a string starting with <code>sk-or-v1-...</code>.
    </div>
    <div class="cl-desc-box" style="background: #FFF4E6; border-left-color: #D9A93B;">
      <strong>⚠ Copy it now.</strong> OpenRouter only shows the full key once. After you close the dialog, you'll only see the prefix <code>sk-or-v1-3d6...</code>. Paste it into a password manager or a sticky note before moving on.
    </div>
    <div style="font-size: 11.5px; color: #888; line-height: 1.5; margin-top: 4px;">
      Tip: name the key <code>hermes-laptop</code> so you remember which device it's for. You can revoke this key any time from the same page.
    </div>
  </div>
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S2-005 · v3</div>

# Step 3 — Connect OpenRouter in the desktop app

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 6px; height: 408px; overflow: hidden; grid-template-rows: minmax(0, 1fr);">
  <div style="position: relative; display: flex; flex-direction: column; border: 1px solid #eadfd8; border-radius: 16px; box-shadow: 0 10px 24px rgba(92,68,56,.10); background: #fff; padding: 10px; overflow: hidden; min-height: 0; height: 100%;">
    <div style="position: absolute; top: 14px; left: 14px; z-index: 2;">
      <span class="cl-image-pill">⑫ PICK OPENROUTER</span>
    </div>
    <img src="/images/12-desktop-provider-picker.jpg" style="width: 100%; height: 100%; object-fit: contain; background: #0a0a0a; border-radius: 8px;">
  </div>
  <div style="display: flex; flex-direction: column; gap: 10px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">On first launch</div>
    <h2 style="margin: 0; font-size: 22px; line-height: 1.25;">Pick OpenRouter, paste your key</h2>
    <div style="font-size: 12.5px; color: #3A3A3A; line-height: 1.5;">
      The desktop app opens a setup wizard on first run. It lists 10 providers — pick <strong>OpenRouter</strong> ("one key, many models"). Paste the <code>sk-or-v1-...</code> key you generated earlier. Click <strong>Connecting</strong>.
    </div>
    <div style="background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; padding: 12px 14px; display: flex; flex-direction: column; gap: 8px;">
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #FF6B35; letter-spacing: 1px;">STEP 1</span>
        <span style="font-size: 12px; color: #2C2C2C;">Click <strong>OpenRouter</strong> card</span>
      </div>
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #FF6B35; letter-spacing: 1px;">STEP 2</span>
        <span style="font-size: 12px; color: #2C2C2C;">Paste your <code>sk-or-v1-...</code> key</span>
      </div>
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #FF6B35; letter-spacing: 1px;">STEP 3</span>
        <span style="font-size: 12px; color: #2C2C2C;">Click <strong>Connecting</strong> (takes ~3 sec)</span>
      </div>
    </div>
    <div class="cl-desc-box">
      <strong>No terminal needed.</strong> The wizard writes your key to <code>~/.hermes/config.yaml</code> automatically.
    </div>
  </div>
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S2-006 · v3</div>

# Step 4 — Switch to a free model

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 6px; height: 408px; overflow: hidden; grid-template-rows: minmax(0, 1fr);">
  <div style="position: relative; display: flex; flex-direction: column; border: 1px solid #eadfd8; border-radius: 16px; box-shadow: 0 10px 24px rgba(92,68,56,.10); background: #fff; padding: 10px; overflow: hidden; min-height: 0; height: 100%;">
    <div style="position: absolute; top: 14px; left: 14px; z-index: 2;">
      <span class="cl-image-pill">⑬ SWITCH TO FREE</span>
    </div>
    <img src="/images/14-desktop-switch-model.jpg" style="width: 100%; height: 100%; object-fit: contain; background: #fafafa; border-radius: 8px;">
  </div>
  <div style="display: flex; flex-direction: column; gap: 10px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">OpenRouter's default isn't free</div>
    <h2 style="margin: 0; font-size: 22px; line-height: 1.25;">Pick one with a [FREE] badge</h2>
    <div style="font-size: 12.5px; color: #3A3A3A; line-height: 1.5;">
      OpenRouter connects to <code>z-ai/glm-5.2</code> by default — a paid model ($0.96 in / $3.01 out per Mtok). Click <strong>Change</strong> in the wizard to switch. The picker lists every OpenRouter model; filter for the green <code>[FREE]</code> badge.
    </div>
    <div style="background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; padding: 12px 14px; display: flex; flex-direction: column; gap: 8px;">
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #FF6B35; letter-spacing: 1px;">STEP 1</span>
        <span style="font-size: 12px; color: #2C2C2C;">Click <strong>Change</strong> next to "Default model"</span>
      </div>
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #FF6B35; letter-spacing: 1px;">STEP 2</span>
        <span style="font-size: 12px; color: #2C2C2C;">Search <code>hy3</code> or <code>llama</code> or <code>qwen</code></span>
      </div>
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #FF6B35; letter-spacing: 1px;">STEP 3</span>
        <span style="font-size: 12px; color: #2C2C2C;">Click any model with <code>[FREE]</code> green badge</span>
      </div>
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #FF6B35; letter-spacing: 1px;">STEP 4</span>
        <span style="font-size: 12px; color: #2C2C2C;">Click <strong>[ BEGIN ]</strong> to start the chat</span>
      </div>
    </div>
    <div class="cl-desc-box">
      <strong>Skip this step?</strong> The default paid model works too — you'll just see a small OpenRouter credit counter on the bottom-left. The free tier has rate limits but no expiry.
    </div>
  </div>
</div>

---
layout: section
---

<div class="cl-ref-id">HM26Q3-S3-001 · v3</div>

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #4FA85C 0%, #6BB57A 100%); display: flex; flex-direction: column; align-items: center; justify-content: center; color: white; text-align: center;">

<div style="font-size: 13px; font-weight: 600; letter-spacing: 4px; opacity: 0.85; margin-bottom: 24px;">
  STEP 3 OF 4
</div>

<h1 style="font-size: 64px; font-weight: 800; color: white; margin: 0; letter-spacing: -1.5px; line-height: 1.1;">
  Pick a free model
</h1>

<div style="font-size: 20px; color: white; opacity: 0.9; margin-top: 28px; max-width: 620px; line-height: 1.4;">
  Three solid choices. Pick one and ship.
</div>

</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S3-002 · v3</div>

# Three free models worth trying

<div style="font-size: 13px; color: #5A5A5A; margin-top: -4px; margin-bottom: 16px; max-width: 720px;">
  All three run on OpenRouter's free tier. Pick one as <code>model.default</code>, swap any time. Speed and quality both vary — try all three for the same prompt and pick what fits your work.
</div>

<div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; margin-top: 8px;">
  <div class="cl-card-white" style="display: flex; flex-direction: column; gap: 10px; border-top: 4px solid #4FA85C;">
    <div class="cl-eyebrow" style="color: #4FA85C;">RECOMMENDED DEFAULT</div>
    <h3 style="margin: 0; font-size: 17px; font-weight: 700; color: #2C2C2C;">Tencent Hy3</h3>
    <div style="font-family: 'JetBrains Mono', monospace; font-size: 11px; color: #888; line-height: 1.4; word-break: break-all;">
      tencent/hy3:free
    </div>
    <div style="font-size: 12.5px; color: #3A3A3A; line-height: 1.55; flex: 1;">
      Strong on English &amp; Chinese, fast, the most generous free quota of the three. The default you've seen running through this deck.
    </div>
    <div style="display: flex; gap: 4px; flex-wrap: wrap; margin-top: 4px;">
      <span style="font-size: 10px; padding: 3px 8px; background: #F4F4F4; border-radius: 4px; color: #555;">Multilingual</span>
      <span style="font-size: 10px; padding: 3px 8px; background: #F4F4F4; border-radius: 4px; color: #555;">Fast</span>
    </div>
  </div>
  <div class="cl-card-white" style="display: flex; flex-direction: column; gap: 10px; border-top: 4px solid #3974C5;">
    <div class="cl-eyebrow" style="color: #3974C5;">REASONING</div>
    <h3 style="margin: 0; font-size: 17px; font-weight: 700; color: #2C2C2C;">NVIDIA Nemotron 3 Super</h3>
    <div style="font-family: 'JetBrains Mono', monospace; font-size: 11px; color: #888; line-height: 1.4; word-break: break-all;">
      nvidia/nemotron-3-super-120b-a12b:free
    </div>
    <div style="font-size: 12.5px; color: #3A3A3A; line-height: 1.55; flex: 1;">
      Massive 120B-parameter MoE model. Slower than Hy3, but stronger on multi-step reasoning. Use this when agent work chains many tool calls.
    </div>
    <div style="display: flex; gap: 4px; flex-wrap: wrap; margin-top: 4px;">
      <span style="font-size: 10px; padding: 3px 8px; background: #F4F4F4; border-radius: 4px; color: #555;">Reasoning</span>
      <span style="font-size: 10px; padding: 3px 8px; background: #F4F4F4; border-radius: 4px; color: #555;">MoE</span>
    </div>
  </div>
  <div class="cl-card-white" style="display: flex; flex-direction: column; gap: 10px; border-top: 4px solid #D0832F;">
    <div class="cl-eyebrow" style="color: #D0832F;">MULTILINGUAL</div>
    <h3 style="margin: 0; font-size: 17px; font-weight: 700; color: #2C2C2C;">NVIDIA Nemotron 3 Ultra</h3>
    <div style="font-family: 'JetBrains Mono', monospace; font-size: 11px; color: #888; line-height: 1.4; word-break: break-all;">
      nvidia/nemotron-3-ultra-550b-a55b:free
    </div>
    <div style="font-size: 12.5px; color: #3A3A3A; line-height: 1.55; flex: 1;">
      550B parameters, NVIDIA's flagship open model. Best free option for English reasoning and long-context work. Slower to first token.
    </div>
    <div style="display: flex; gap: 4px; flex-wrap: wrap; margin-top: 4px;">
      <span style="font-size: 10px; padding: 3px 8px; background: #F4F4F4; border-radius: 4px; color: #555;">Long context</span>
      <span style="font-size: 10px; padding: 3px 8px; background: #F4F4F4; border-radius: 4px; color: #555;">Code</span>
    </div>
  </div>
</div>

<div style="display: flex; justify-content: space-between; align-items: center; padding: 12px 16px; background: #FFFFFF; border: 1px solid #FF6B35; border-radius: 10px; margin-top: 22px;">
  <div>
    <strong style="font-size: 13px; color: #2C2C2C;">Want the full live list?</strong>
    <div style="font-size: 11.5px; color: #888; margin-top: 2px;">OpenRouter updates free models often — this link always shows the current ones.</div>
  </div>
  <a href="https://openrouter.ai/models?q=free" target="_blank" rel="noopener" style="display: inline-block; padding: 8px 16px; background: #FF6B35; color: white; border-radius: 6px; font-size: 12px; font-weight: 600; text-decoration: none; letter-spacing: 0.3px; white-space: nowrap;">Browse free models ↗</a>
</div>

---
layout: section
---

<div class="cl-ref-id">HM26Q3-S4-001 · v3</div>

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #D0832F 0%, #E8A656 100%); display: flex; flex-direction: column; align-items: center; justify-content: center; color: white; text-align: center;">

<div style="font-size: 13px; font-weight: 600; letter-spacing: 4px; opacity: 0.85; margin-bottom: 24px;">
  STEP 4 OF 4
</div>

<h1 style="font-size: 64px; font-weight: 800; color: white; margin: 0; letter-spacing: -1.5px; line-height: 1.1;">
  Your first chat
</h1>

<div style="font-size: 20px; color: white; opacity: 0.9; margin-top: 28px; max-width: 620px; line-height: 1.4;">
  Launch the desktop app and see it work.
</div>

</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S4-002 · v3</div>

# Launch Hermes Desktop

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 6px; height: 408px; overflow: hidden; grid-template-rows: minmax(0, 1fr);">
  <div style="position: relative; display: flex; flex-direction: column; border: 1px solid #eadfd8; border-radius: 16px; box-shadow: 0 10px 24px rgba(92,68,56,.10); background: #fff; padding: 10px; overflow: hidden; min-height: 0; height: 100%;">
    <div style="position: absolute; top: 14px; left: 14px; z-index: 2;">
      <span class="cl-image-pill">⑦ DESKTOP UI</span>
    </div>
    <img src="/images/07-desktop-chat.png" style="width: 100%; height: 100%; object-fit: contain; background: #fafafa; border-radius: 8px;">
  </div>
  <div style="display: flex; flex-direction: column; gap: 12px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">Three ways to open it</div>
    <h2 style="margin: 0; font-size: 22px; line-height: 1.25;">Start menu, terminal, or CLI</h2>
    <div style="font-size: 13px; color: #3A3A3A; line-height: 1.55;">
      <strong>① Start menu</strong> → search "Hermes" → click the desktop icon.<br>
      <strong>② Terminal</strong> → type <code>hermes desktop</code> and hit Enter.<br>
      <strong>③ CLI-only</strong> → type <code>hermes</code> for the in-terminal chat UI (lighter on memory).
    </div>
    <div class="cl-desc-box">
      <strong>The screenshot on the left</strong> is a real session. Sidebar: <code>New session</code> / <code>Capabilities</code> / <code>Messaging</code> / <code>Artifacts</code>. Bottom-right shows the active model. The chat is streaming — you'll see <code>Thinking</code> → <code>Skill View</code> → tool calls → final reply.
    </div>
    <div style="font-size: 11.5px; color: #888; line-height: 1.5;">
      First launch takes ~10 seconds while the backend warms up. You can keep the app open across sessions — it'll remember everything.
    </div>
  </div>
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S4-003 · v3</div>

# Type your first prompt

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 6px; height: 408px; overflow: hidden; grid-template-rows: minmax(0, 1fr);">
  <div style="display: flex; flex-direction: column; gap: 8px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">Try one of these</div>
    <h2 style="margin: 0; font-size: 20px; line-height: 1.25;">Three prompts that show off what Hermes can do</h2>
    <div style="font-size: 11.5px; color: #5A5A5A; line-height: 1.4;">
      The agent will think, possibly call a tool, and stream a reply. First = warm-up; second and third show real tool use.
    </div>
    <div style="background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; padding: 10px 12px; display: flex; flex-direction: column; gap: 4px;">
      <div style="display: flex; align-items: center; gap: 8px;">
        <span style="font-size: 9.5px; font-weight: 700; color: white; background: #4FA85C; padding: 2px 7px; border-radius: 4px; letter-spacing: 1px;">EASY</span>
        <strong style="font-size: 13px; color: #2C2C2C;">Warm-up chat</strong>
      </div>
      <div style="font-style: italic; font-size: 12px; color: #3A3A3A; line-height: 1.45;">
        "Explain in 3 sentences what you can do that a normal chatbot can't."
      </div>
    </div>
    <div style="background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; padding: 10px 12px; display: flex; flex-direction: column; gap: 4px;">
      <div style="display: flex; align-items: center; gap: 8px;">
        <span style="font-size: 9.5px; font-weight: 700; color: white; background: #3974C5; padding: 2px 7px; border-radius: 4px; letter-spacing: 1px;">TOOL USE</span>
        <strong style="font-size: 13px; color: #2C2C2C;">Read a file</strong>
      </div>
      <div style="font-style: italic; font-size: 12px; color: #3A3A3A; line-height: 1.45;">
        "Read <code>~/.hermes/config.yaml</code> and tell me what model is set as default."
      </div>
    </div>
    <div style="background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; padding: 10px 12px; display: flex; flex-direction: column; gap: 4px;">
      <div style="display: flex; align-items: center; gap: 8px;">
        <span style="font-size: 9.5px; font-weight: 700; color: white; background: #7C3AED; padding: 2px 7px; border-radius: 4px; letter-spacing: 1px;">MULTI-STEP</span>
        <strong style="font-size: 13px; color: #2C2C2C;">Run a real task</strong>
      </div>
      <div style="font-style: italic; font-size: 12px; color: #3A3A3A; line-height: 1.45;">
        "Make a <code>notes/</code> folder on my Desktop and inside it write <code>today.md</code> with the date and a 3-bullet to-do list I can edit."
      </div>
    </div>
  </div>
  <div style="display: flex; flex-direction: column; gap: 8px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">What good looks like</div>
    <h2 style="margin: 0; font-size: 19px; line-height: 1.25;">It's not just chat</h2>
    <div style="font-size: 12px; color: #3A3A3A; line-height: 1.45;">
      A real reply streams in over a few seconds. You'll see lines like <code>Skill View 72ms</code> scroll past as Hermes works. Then a final answer.
    </div>
    <div class="cl-desc-box" style="padding: 10px 14px;">
      <strong>You stay in control:</strong> Hermes asks before any shell command that looks destructive. You see the command, you approve or deny.
    </div>
    <div style="background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; padding: 10px 12px;">
      <div style="font-size: 10px; color: #888; letter-spacing: 1px; font-weight: 700; margin-bottom: 5px;">SAMPLE REPLY</div>
      <div style="font-family: 'JetBrains Mono', monospace; font-size: 10px; color: #5A6470; line-height: 1.5;">
        <span style="color: #4FA85C;">●</span> Thinking — read config...<br>
        <span style="color: #4FA85C;">●</span> Skill View 80ms<br>
        <span style="color: #FF6B35;">→</span> Default model: <code>tencent/hy3:free</code><br>
        <span style="color: #4FA85C;">●</span> Done.
      </div>
    </div>
    <div style="font-size: 10.5px; color: #888; line-height: 1.5;">
      Skip approvals with <code>--yolo</code> (not recommended for first run).
    </div>
  </div>
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-S4-004 · v3</div>

# A real example — what you can do in one chat

<div style="display: grid; grid-template-columns: 1.05fr .95fr; gap: 22px; margin-top: 6px; height: 408px; overflow: hidden; grid-template-rows: minmax(0, 1fr);">
  <div style="position: relative; display: flex; flex-direction: column; border: 1px solid #eadfd8; border-radius: 16px; box-shadow: 0 10px 24px rgba(92,68,56,.10); background: #fff; padding: 10px; overflow: hidden; min-height: 0; height: 100%;">
    <div style="position: absolute; top: 14px; left: 14px; z-index: 2;">
      <span class="cl-image-pill">⑱ REAL OUTPUT</span>
    </div>
    <img src="/images/10-final-ppt.png" style="width: 100%; height: 100%; object-fit: contain; background: #fff; border-radius: 8px;">
  </div>
  <div style="display: flex; flex-direction: column; gap: 12px; overflow: hidden; min-height: 0;">
    <div class="cl-eyebrow">This deck is built by Hermes</div>
    <h2 style="margin: 0; font-size: 22px; line-height: 1.25;">From one prompt to a finished PowerPoint slide</h2>
    <div style="font-size: 12.5px; color: #3A3A3A; line-height: 1.5;">
      The screenshot on the left is the result of a single chat with Hermes. The user typed:
    </div>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 10px; padding: 14px 16px; font-family: 'JetBrains Mono', monospace; font-size: 12px; line-height: 1.7;">
      <div style="color: #888; font-size: 10.5px; margin-bottom: 4px;">YOU TYPE</div>
      <div style="color: #FF8C42;">"Use this PDF to create 1 PowerPoint slide that introduces the Smart Watch 4G."</div>
    </div>
    <div style="font-size: 12.5px; color: #3A3A3A; line-height: 1.5;">
      Hermes then:
    </div>
    <div style="background: #FFFFFF; border: 1px solid #E5E5E5; border-radius: 10px; padding: 12px 14px; display: flex; flex-direction: column; gap: 6px;">
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #4FA85C; letter-spacing: 1px;">①</span>
        <span style="font-size: 12px; color: #2C2C2C;">Read the PDF with <code>pymupdf</code> (installed automatically)</span>
      </div>
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #4FA85C; letter-spacing: 1px;">②</span>
        <span style="font-size: 12px; color: #2C2C2C;">Wrote a <code>extract_pdf.py</code> script and ran it</span>
      </div>
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #4FA85C; letter-spacing: 1px;">③</span>
        <span style="font-size: 12px; color: #2C2C2C;">Used a subagent to QA the spec sheet</span>
      </div>
      <div style="display: flex; align-items: baseline; gap: 10px;">
        <span style="font-size: 11px; font-weight: 700; color: #4FA85C; letter-spacing: 1px;">④</span>
        <span style="font-size: 12px; color: #2C2C2C;">Generated the final <code>SmartWatch_Intro.pptx</code></span>
      </div>
    </div>
    <div class="cl-desc-box">
      <strong>Why this matters:</strong> zero PowerPoint skills needed. You asked in English, Hermes wrote Python, ran it, and gave you a file. The same pattern works for Excel, PDFs, web scraping, file conversion — anything you can describe.
    </div>
  </div>
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-TRB-001 · v3</div>

# Three things that go wrong (and how to fix them)

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-top: 18px; max-width: 880px; margin-left: auto; margin-right: auto;">
  <div class="cl-card-white" style="display: flex; flex-direction: column; gap: 8px; border-top: 4px solid #D8556A; padding: 14px 16px;">
    <div class="cl-eyebrow" style="color: #D8556A;">ERROR</div>
    <h3 style="margin: 0; font-size: 15px; font-weight: 700; color: #2C2C2C;">"HTTP 400: No models provided"</h3>
    <div style="font-family: 'JetBrains Mono', monospace; font-size: 10.5px; color: #888; line-height: 1.4;">
      <strong>Cause:</strong> <code>config.yaml</code> saved with a UTF-8 BOM (Notepad does this).
    </div>
    <div style="font-size: 12px; color: #3A3A3A; line-height: 1.5; flex: 1;">
      Re-save as UTF-8 <em>without</em> BOM. Run <code>hermes config edit</code> — it writes cleanly.
    </div>
  </div>
  <div class="cl-card-white" style="display: flex; flex-direction: column; gap: 8px; border-top: 4px solid #D9A93B; padding: 14px 16px;">
    <div class="cl-eyebrow" style="color: #D9A93B;">SLOW</div>
    <h3 style="margin: 0; font-size: 15px; font-weight: 700; color: #2C2C2C;">First reply takes 30+ seconds</h3>
    <div style="font-family: 'JetBrains Mono', monospace; font-size: 10.5px; color: #888; line-height: 1.4;">
      <strong>Cause:</strong> OpenRouter is cold-starting the model, or you're rate-limited.
    </div>
    <div style="font-size: 12px; color: #3A3A3A; line-height: 1.5; flex: 1;">
      Wait. If it persists past a minute, switch model with <code>hermes model</code> and try a different free model.
    </div>
  </div>
  <div class="cl-card-white" style="display: flex; flex-direction: column; gap: 8px; border-top: 4px solid #3974C5; padding: 14px 16px;">
    <div class="cl-eyebrow" style="color: #3974C5;">STUCK</div>
    <h3 style="margin: 0; font-size: 15px; font-weight: 700; color: #2C2C2C;">Agent hangs on a tool call</h3>
    <div style="font-family: 'JetBrains Mono', monospace; font-size: 10.5px; color: #888; line-height: 1.4;">
      <strong>Cause:</strong> network timeout, or the model is stuck waiting on you.
    </div>
    <div style="font-size: 12px; color: #3A3A3A; line-height: 1.5; flex: 1;">
      In the desktop app: press <strong>Esc</strong> or click the stop button. In the CLI: <code>Ctrl+C</code>. Then <code>/retry</code> to send the prompt again.
    </div>
  </div>
  <div class="cl-card-white" style="display: flex; flex-direction: column; gap: 8px; border-top: 4px solid #7C3AED; padding: 14px 16px;">
    <div class="cl-eyebrow" style="color: #7C3AED;">STILL BROKEN</div>
    <h3 style="margin: 0; font-size: 15px; font-weight: 700; color: #2C2C2C;">Nothing above matches</h3>
    <div style="font-family: 'JetBrains Mono', monospace; font-size: 10.5px; color: #888; line-height: 1.4;">
      <strong>One command:</strong> <code>hermes doctor</code>
    </div>
    <div style="font-size: 12px; color: #3A3A3A; line-height: 1.5; flex: 1;">
      Checks every dependency, every config value, every API key. Add <code>--fix</code> for auto-repair.
    </div>
  </div>
</div>

---
layout: default
---

<div class="cl-ref-id">HM26Q3-END-001 · v3</div>

# You're set up

<div style="font-size: 16px; color: #3A3A3A; line-height: 1.55; margin-top: 6px; max-width: 720px;">
  You have Hermes Desktop running on Windows, pointed at OpenRouter's free tier, and you've sent it a prompt. Everything else is upside.
</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-top: 16px; max-width: 880px;">
  <div class="cl-card" style="display: flex; flex-direction: column; gap: 6px; padding: 14px 16px;">
    <div class="cl-eyebrow">LEVEL 2 — SKILLS</div>
    <h3 style="margin: 0; font-size: 16px; font-weight: 700; color: #2C2C2C;">Teach it your workflow</h3>
    <div style="font-size: 12px; color: #5A5A5A; line-height: 1.5;">
      <code>hermes skills browse</code> installs community skills (Telegram bots, PDF readers, etc.).
    </div>
  </div>
  <div class="cl-card" style="display: flex; flex-direction: column; gap: 6px; padding: 14px 16px;">
    <div class="cl-eyebrow" style="color: #7C3AED;">LEVEL 3 — MEMORY</div>
    <h3 style="margin: 0; font-size: 16px; font-weight: 700; color: #2C2C2C;">It remembers next session</h3>
    <div style="font-size: 12px; color: #5A5A5A; line-height: 1.5;">
      <code>/memory</code> stores facts about you. Tell it "I use VS Code" once, never again.
    </div>
  </div>
  <div class="cl-card" style="display: flex; flex-direction: column; gap: 6px; padding: 14px 16px;">
    <div class="cl-eyebrow" style="color: #4FA85C;">LEVEL 4 — MESSAGING</div>
    <h3 style="margin: 0; font-size: 16px; font-weight: 700; color: #2C2C2C;">Run it on Telegram / Discord</h3>
    <div style="font-size: 12px; color: #5A5A5A; line-height: 1.5;">
      <code>hermes gateway setup</code> connects 20+ chat platforms.
    </div>
  </div>
  <div class="cl-card" style="display: flex; flex-direction: column; gap: 6px; padding: 14px 16px;">
    <div class="cl-eyebrow" style="color: #D0832F;">LEVEL 5 — CRON</div>
    <h3 style="margin: 0; font-size: 16px; font-weight: 700; color: #2C2C2C;">Schedule it to run</h3>
    <div style="font-size: 12px; color: #5A5A5A; line-height: 1.5;">
      <code>hermes cron create</code> makes the agent run on a timer.
    </div>
  </div>
</div>

<div style="display: flex; justify-content: center; align-items: center; gap: 10px; margin-top: 12px; flex-wrap: wrap;">
  <a href="https://hermes-agent.nousresearch.com/docs/" target="_blank" rel="noopener" style="display: inline-block; padding: 7px 14px; background: #FF6B35; color: white; border-radius: 6px; font-size: 12px; font-weight: 600; text-decoration: none; letter-spacing: 0.3px;">Read the docs ↗</a>
  <span style="font-size: 12px; color: #888;">or type <code>/help</code> in the chat any time.</span>
</div>

<div style="position: absolute; bottom: 28px; left: 50px; font-size: 11px; color: #999;">
  HM26Q3 · 21 slides · ~30 minutes · Hermes Agent v0.18+
</div>