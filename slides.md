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

# Hermes Agent
# <span style="color: #FF6B35;">Install & Use</span>

A step-by-step walkthrough for new users

<div style="margin-top: 28px;">
  <span style="display: inline-block; background: rgba(255, 107, 53, 0.12); color: #FF6B35; border-radius: 999px; padding: 4px 12px; font-size: 12px; font-weight: 600;">Ref: HM26Q3-COV-001</span>
  <span style="display: inline-block; background: rgba(255, 107, 53, 0.12); color: #FF6B35; border-radius: 999px; padding: 4px 12px; font-size: 12px; font-weight: 600; margin-left: 8px;">Charles Lo · 2026-07</span>
</div>

---
layout: default
---

# What you'll learn

Six sections, end-to-end. From `curl install` to a working bot on Telegram.

<div class="grid grid-cols-2 gap-3" style="margin-top: 8px;">
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-left: 4px solid #FF6B35; border-radius: 10px; padding: 9px 14px;">
    <div style="font-size: 18px; font-weight: 800; color: #FF6B35; line-height: 1;">01</div>
    <div style="font-size: 14px; font-weight: 700; color: #2C2C2C; margin-top: 4px;">Install</div>
    <div style="font-size: 11.5px; color: #6B6B6B; margin-top: 3px; line-height: 1.35;">Desktop installer, curl one-liner, or PowerShell. Pick your platform.</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-left: 4px solid #FF6B35; border-radius: 10px; padding: 9px 14px;">
    <div style="font-size: 18px; font-weight: 800; color: #FF6B35; line-height: 1;">02</div>
    <div style="font-size: 14px; font-weight: 700; color: #2C2C2C; margin-top: 4px;">Choose a provider</div>
    <div style="font-size: 11.5px; color: #6B6B6B; margin-top: 3px; line-height: 1.35;">Three setup modes — Nous Portal fastest, Full for control, Blank Slate minimal.</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-left: 4px solid #FF6B35; border-radius: 10px; padding: 9px 14px;">
    <div style="font-size: 18px; font-weight: 800; color: #FF6B35; line-height: 1;">03</div>
    <div style="font-size: 14px; font-weight: 700; color: #2C2C2C; margin-top: 4px;">First chat</div>
    <div style="font-size: 11.5px; color: #6B6B6B; margin-top: 3px; line-height: 1.35;">CLI vs TUI, the welcome banner, and three starter prompts that prove the agent works.</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-left: 4px solid #FF6B35; border-radius: 10px; padding: 9px 14px;">
    <div style="font-size: 18px; font-weight: 800; color: #FF6B35; line-height: 1;">04</div>
    <div style="font-size: 14px; font-weight: 700; color: #2C2C2C; margin-top: 4px;">Verify sessions</div>
    <div style="font-size: 11.5px; color: #6B6B6B; margin-top: 3px; line-height: 1.35;">Make sure <code style="font-size: 11px;">hermes --continue</code> works before you juggle profiles.</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-left: 4px solid #FF6B35; border-radius: 10px; padding: 9px 14px;">
    <div style="font-size: 18px; font-weight: 800; color: #FF6B35; line-height: 1;">05</div>
    <div style="font-size: 14px; font-weight: 700; color: #2C2C2C; margin-top: 4px;">Key features</div>
    <div style="font-size: 11.5px; color: #6B6B6B; margin-top: 3px; line-height: 1.35;">Terminal, slash commands, multi-line input, interrupt.</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-left: 4px solid #FF8C42; border-radius: 10px; padding: 9px 14px; grid-column: span 2;">
    <div style="font-size: 18px; font-weight: 800; color: #FF6B35; line-height: 1;">06</div>
    <div style="font-size: 14px; font-weight: 700; color: #2C2C2C; margin-top: 4px;">Next layer + When it breaks · Q&A</div>
    <div style="font-size: 11.5px; color: #6B6B6B; margin-top: 3px; line-height: 1.35;">Bots, skills, MCP, voice, ACP — and the failure modes + recovery toolkit that fix the rest.</div>
  </div>
</div>

---
layout: default
---

# The fastest path

Pick the row that matches your goal. **Rule of thumb:** if Hermes cannot complete a normal chat, do not add more features yet. Get one clean conversation working first.

<div style="margin-top: 18px; border: 1px solid #ECECEC; border-radius: 10px; overflow: hidden;">
  <div style="display: grid; grid-template-columns: 1.2fr 1.2fr 1.2fr; gap: 8px; padding: 8px 12px; font-size: 13px; font-weight: 700; color: #2C2C2C; background: #FFF8F4; border-bottom: 1px solid #ECECEC; align-items: center;">
    <div>Goal</div><div>Do this first</div><div>Then do this</div>
  </div>
  <div style="display: grid; grid-template-columns: 1.2fr 1.2fr 1.2fr; gap: 8px; padding: 8px 12px; font-size: 13px; border-bottom: 1px solid #ECECEC; align-items: center;">
    <div>I just want Hermes working on my machine</div>
    <div><code>hermes setup</code></div>
    <div>Run a real chat and verify it responds</div>
  </div>
  <div style="display: grid; grid-template-columns: 1.2fr 1.2fr 1.2fr; gap: 8px; padding: 8px 12px; font-size: 13px; border-bottom: 1px solid #ECECEC; align-items: center;">
    <div>I already know my provider</div>
    <div><code>hermes model</code></div>
    <div>Save the config, then start chatting</div>
  </div>
  <div style="display: grid; grid-template-columns: 1.2fr 1.2fr 1.2fr; gap: 8px; padding: 8px 12px; font-size: 13px; border-bottom: 1px solid #ECECEC; align-items: center;">
    <div>I want a bot or always-on setup</div>
    <div><code>hermes gateway setup</code> (after CLI works)</div>
    <div>Connect Telegram, Discord, Slack, or another platform</div>
  </div>
  <div style="display: grid; grid-template-columns: 1.2fr 1.2fr 1.2fr; gap: 8px; padding: 8px 12px; font-size: 13px; border-bottom: 1px solid #ECECEC; align-items: center;">
    <div>I want a local or self-hosted model</div>
    <div><code>hermes model</code> → custom endpoint</div>
    <div>Verify endpoint, model name, and ≥64K context</div>
  </div>
  <div style="display: grid; grid-template-columns: 1.2fr 1.2fr 1.2fr; gap: 8px; padding: 8px 12px; font-size: 13px; align-items: center;">
    <div>I want multi-provider fallback</div>
    <div><code>hermes model</code> first</div>
    <div>Add routing and fallback only after the base chat works</div>
  </div>
</div>

---
layout: default
---

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%); color: white; display: flex; flex-direction: column; justify-content: center; padding: 60px 80px;">

# Section 01
# <span style="color: white;">Install</span>

<div style="margin-top: 20px; font-size: 18px; opacity: 0.92;">Get Hermes Agent onto your machine — three paths, one command.</div>

</div>

---
layout: default
---

# Install — Desktop installer (recommended on macOS / Windows)

The easiest path. Downloads both the CLI and the desktop app from one installer, runs them in the right places.

<div class="grid grid-cols-2 gap-6" style="margin-top: 22px;">
  <div>
    <h3 style="color: #FF6B35; margin-top: 0;">What you get</h3>
    <ul style="font-size: 14px; line-height: 1.7; color: #2C2C2C;">
      <li>The <strong>CLI binary</strong> on your PATH (<code>hermes</code>, <code>hermes --tui</code>)</li>
      <li>The <strong>desktop app</strong> (chat UI, session browser)</li>
      <li>Default skills installed to <code>~/.hermes/skills/</code></li>
      <li>No manual PATH edits, no shell reload</li>
    </ul>
    <a href="https://hermes-agent.nousresearch.com/" target="_blank" style="display: inline-block; padding: 14px 22px; background: #FF6B35; color: white; border-radius: 8px; font-weight: 600; text-decoration: none; box-shadow: 0 4px 14px rgba(255, 107, 53, 0.35); letter-spacing: 0.3px; margin-top: 14px;">Download Hermes Desktop →</a>
  </div>
  <div>
    <div style="background: #FFF8F4; border: 1px solid rgba(255, 107, 53, 0.25); border-radius: 12px; padding: 16px 18px;">
      <h3 style="color: #FF6B35; margin-top: 0;">Use this when</h3>
      <ul style="font-size: 13px; line-height: 1.6; color: #2C2C2C; margin: 0; padding-left: 18px;">
        <li>You're on macOS or Windows desktop</li>
        <li>You want a GUI alongside the CLI</li>
        <li>You're not sure which install path to take</li>
      </ul>
    </div>
    <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 16px 18px; margin-top: 14px;">
      <h3 style="color: #FF6B35; margin-top: 0;">After install</h3>
      <p style="margin: 0; color: #6B6B6B; font-size: 13px; line-height: 1.5;">Skip straight to <strong style="color: #2C2C2C;">section 2 — Choose a Provider</strong>. The installer handles shell reload and config dir creation for you.</p>
    </div>
  </div>
</div>

---
layout: default
---

# Install — curl / PowerShell (no Desktop)

For Linux, WSL2, Android (Termux), and Windows native without the GUI.

<div class="grid grid-cols-2 gap-6" style="margin-top: 18px;">
  <div>
    <h3 style="color: #FF6B35; margin-top: 0; font-size: 15px;">Linux / macOS / WSL2 / Android (Termux)</h3>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 8px; padding: 12px 14px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 12px; line-height: 1.5; box-shadow: 0 4px 16px rgba(0, 0, 0, 0.18);">
      <div><span style="color: #5EC4A8;">$</span> <span style="color: #FF8C42;">curl -fsSL https://hermes-agent.nousresearch.com/install.sh</span> <span style="color: #888; font-style: italic;">\</span></div>
      <div>&nbsp;&nbsp;&nbsp;<span style="color: #888; font-style: italic;">|</span> bash</div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 8px 0 4px;">After it finishes, reload your shell:</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 6px; padding: 7px 12px; font-family: 'JetBrains Mono', monospace; font-size: 11.5px; margin: 0; display: inline-block;"><span style="color: #5EC4A8;">$</span> source ~/.bashrc   <span style="color: #888;"># or source ~/.zshrc</span></div>
    <h3 style="color: #FF6B35; margin: 16px 0 4px; font-size: 14px;">Android / Termux — phone install</h3>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0; line-height: 1.45;">On a phone? See the <a href="https://hermes-agent.nousresearch.com/docs/getting-started/termux" target="_blank" style="color: #FF6B35; font-weight: 600;">Termux guide</a> for the tested manual path and current Android limits.</p>
  </div>
  <div>
    <h3 style="color: #FF6B35; margin-top: 0; font-size: 15px;">Windows (native, PowerShell)</h3>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 8px; padding: 12px 14px; font-family: 'JetBrains Mono', monospace; font-size: 12px; line-height: 1.5; box-shadow: 0 4px 16px rgba(0, 0, 0, 0.18);">
      <div><span style="color: #5EC4A8;">&gt;</span> iex (irm https://hermes-agent.nousresearch.com/install.ps1)</div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 8px 0 4px;">Run PowerShell as Administrator if the install path is protected.</p>
    <h3 style="color: #FF6B35; margin: 16px 0 4px; font-size: 14px;">For detailed options</h3>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0; line-height: 1.45;">Prerequisites, alternative paths, troubleshooting — see the <a href="https://hermes-agent.nousresearch.com/docs/getting-started/installation" target="_blank" style="color: #FF6B35; font-weight: 600;">Installation guide</a>.</p>
  </div>
</div>

---
layout: default
---

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%); color: white; display: flex; flex-direction: column; justify-content: center; padding: 60px 80px;">

# Section 02
# <span style="color: white;">Choose a Provider</span>

<div style="margin-top: 20px; font-size: 18px; opacity: 0.92;">The single most important setup step. Pick a model, set keys, save the config.</div>

</div>

---
layout: default
---

# Three setup modes

`hermes setup` walks you through it. Pick the mode that matches how much you want to control.

<div class="grid grid-cols-3 gap-4" style="margin-top: 22px;">
  <div style="background: linear-gradient(180deg, #FFFFFF 0%, #FFF8F4 100%); border: 2px solid #FF6B35; border-radius: 12px; padding: 16px 18px; box-shadow: 0 4px 14px rgba(255, 107, 53, 0.12);">
    <div style="display: inline-block; background: #FF6B35; color: white; border-radius: 999px; padding: 3px 10px; font-size: 10.5px; font-weight: 700; letter-spacing: 0.6px;">RECOMMENDED</div>
    <h3 style="margin: 8px 0 4px; font-size: 17px; color: #2C2C2C;">Quick Setup · Nous Portal</h3>
    <p style="margin: 0; color: #6B6B6B; font-size: 13px; line-height: 1.5;">Free OAuth login, no API keys. Sets up a model <strong>plus</strong> the Tool Gateway (web search, image gen, TTS, cloud browser) in one step.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 6px; padding: 8px 12px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 12.5px; margin-top: 12px;"><span style="color: #5EC4A8;">$</span> hermes setup --portal</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 16px 18px;">
    <h3 style="margin: 0 0 6px; font-size: 17px; color: #2C2C2C;">Full Setup</h3>
    <p style="margin: 0; color: #6B6B6B; font-size: 13px; line-height: 1.5;">Walk through every provider, tool, and option yourself. <strong>Bring your own keys.</strong></p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 6px; padding: 8px 12px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 12.5px; margin-top: 12px;"><span style="color: #5EC4A8;">$</span> hermes setup</div>
    <p style="font-size: 11.5px; color: #999; margin-top: 8px;">Pick this when you need to control every tool and skill.</p>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 16px 18px;">
    <h3 style="margin: 0 0 6px; font-size: 17px; color: #2C2C2C;">Blank Slate</h3>
    <p style="margin: 0; color: #6B6B6B; font-size: 13px; line-height: 1.5;">Minimal baseline only: provider, model, file ops, terminal. <strong>Everything else off.</strong> Enable features later as you need them.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 6px; padding: 8px 12px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 12.5px; margin-top: 12px;"><span style="color: #888;">(choose "Blank Slate" in the wizard)</span></div>
  </div>
</div>

<div style="margin-top: 18px; padding: 10px 14px; background: rgba(255, 107, 53, 0.08); border-left: 3px solid #FF6B35; border-radius: 6px; font-size: 13px;">
  <strong style="color: #FF6B35;">Switch any time</strong> — `hermes setup` is interactive and idempotent. You can also run <code style="background: #FFF; padding: 1px 5px; border-radius: 3px;">hermes model</code> to swap providers without re-running the whole wizard.
</div>

---
layout: default
---

# The recommended fast path — `hermes setup --portal`

One command, one login. Sets the model <strong>and</strong> the Tool Gateway.

<div class="grid grid-cols-2 gap-6" style="margin-top: 22px;">
  <div>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 10px; padding: 14px 16px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 12.5px; line-height: 1.55; box-shadow: 0 6px 20px rgba(0, 0, 0, 0.18);">
      <div><span style="color: #5EC4A8;">$</span> <span style="color: #FF8C42;">hermes setup --portal</span></div>
      <div style="color: #B8B8B8;">› opening browser for Nous Portal login…</div>
      <div style="color: #B8B8B8;">› waiting for OAuth callback…</div>
      <div style="color: #6FCF97;">✓ logged in as charles@…</div>
      <div style="color: #B8B8B8;">› selecting default model: <span style="color: #FF8C42;">claude-opus-4.6</span></div>
      <div style="color: #6FCF97;">✓ Tool Gateway enabled (web, image, TTS, browser)</div>
      <div style="color: #6FCF97;">✓ config saved to ~/.hermes/config.yaml</div>
      <div style="color: #B8B8B8;">› run <span style="color: #FF8C42;">hermes</span> to start chatting</div>
    </div>
  </div>
  <div>
    <h3 style="color: #FF6B35; margin-top: 0;">What the Portal gives you</h3>
    <ul style="font-size: 13px; line-height: 1.7; color: #2C2C2C;">
      <li><strong>300+ models</strong> on one subscription — no per-provider API key juggling.</li>
      <li><strong>Tool Gateway</strong> — web search, image generation, TTS, and a cloud browser, all pre-configured.</li>
      <li>You can still swap to any other provider later with <code>hermes model</code>.</li>
    </ul>
    <div style="background: #FFF8F4; border: 1px solid rgba(255, 107, 53, 0.25); border-radius: 10px; padding: 12px 14px; margin-top: 12px; font-size: 12.5px;">
      <strong style="color: #FF6B35;">No lock-in.</strong> Switching providers is one command: <code style="background: #1E1E1E; color: #E6E6E6; padding: 1px 5px; border-radius: 3px;">hermes model</code>.
    </div>
  </div>
</div>

---
layout: default
---

# Provider catalog (the 6 most-picked)

An excerpt from 30+ supported. Most users only ever need one of these.

<div style="margin-top: 12px; border: 1px solid #ECECEC; border-radius: 10px; overflow: hidden; font-size: 12px;">
  <div style="display: grid; grid-template-columns: 1.1fr 1.6fr 1.5fr; gap: 6px; padding: 7px 12px; font-weight: 700; color: #2C2C2C; background: #FFF8F4; border-bottom: 1px solid #ECECEC;">
    <div>Provider</div><div>What it is</div><div>How to set up</div>
  </div>
  <div style="display: grid; grid-template-columns: 1.1fr 1.6fr 1.5fr; gap: 6px; padding: 5px 12px; border-bottom: 1px solid #ECECEC;">
    <div><strong>Nous Portal</strong></div>
    <div>Subscription, zero-config, 300+ models + Tool Gateway</div>
    <div>OAuth via <code style="font-size: 11px;">hermes model</code> (or <code style="font-size: 11px;">--portal</code>)</div>
  </div>
  <div style="display: grid; grid-template-columns: 1.1fr 1.6fr 1.5fr; gap: 6px; padding: 5px 12px; border-bottom: 1px solid #ECECEC;">
    <div><strong>Anthropic</strong></div>
    <div>Claude — Max plan OAuth or API key</div>
    <div><code style="font-size: 11px;">hermes model</code> → OAuth, or <code style="font-size: 11px;">ANTHROPIC_API_KEY</code></div>
  </div>
  <div style="display: grid; grid-template-columns: 1.1fr 1.6fr 1.5fr; gap: 6px; padding: 5px 12px; border-bottom: 1px solid #ECECEC;">
    <div><strong>OpenAI Codex</strong></div>
    <div>ChatGPT OAuth, Codex models</div>
    <div>Device code auth via <code style="font-size: 11px;">hermes model</code></div>
  </div>
  <div style="display: grid; grid-template-columns: 1.1fr 1.6fr 1.5fr; gap: 6px; padding: 5px 12px; border-bottom: 1px solid #ECECEC;">
    <div><strong>OpenRouter</strong></div>
    <div>Multi-provider routing, many models</div>
    <div><code style="font-size: 11px;">OPENROUTER_API_KEY</code></div>
  </div>
  <div style="display: grid; grid-template-columns: 1.1fr 1.6fr 1.5fr; gap: 6px; padding: 5px 12px; border-bottom: 1px solid #ECECEC;">
    <div><strong>Google AI Studio</strong></div>
    <div>Gemini direct API</div>
    <div><code style="font-size: 11px;">GOOGLE_API_KEY</code> / <code style="font-size: 11px;">GEMINI_API_KEY</code></div>
  </div>
  <div style="display: grid; grid-template-columns: 1.1fr 1.6fr 1.5fr; gap: 6px; padding: 5px 12px; border-bottom: 1px solid #ECECEC;">
    <div><strong>GitHub Copilot</strong></div>
    <div>GPT-5.x / Claude / Gemini via subscription</div>
    <div>OAuth via <code style="font-size: 11px;">hermes model</code> or <code style="font-size: 11px;">COPILOT_GITHUB_TOKEN</code></div>
  </div>
  <div style="display: grid; grid-template-columns: 1.1fr 1.6fr 1.5fr; gap: 6px; padding: 5px 12px; border-bottom: 1px solid #ECECEC;">
    <div><strong>DeepSeek</strong></div>
    <div>Direct DeepSeek API</div>
    <div><code style="font-size: 11px;">DEEPSEEK_API_KEY</code></div>
  </div>
  <div style="display: grid; grid-template-columns: 1.1fr 1.6fr 1.5fr; gap: 6px; padding: 5px 12px;">
    <div><strong>Custom Endpoint</strong></div>
    <div>VLLM / SGLang / Ollama / any OpenAI-compatible</div>
    <div>Base URL + API key in <code style="font-size: 11px;">config.yaml</code></div>
  </div>
</div>

<div style="margin-top: 10px; padding: 9px 14px; background: #FFF8F4; border-radius: 8px; font-size: 12px; color: #6B6B6B; display: flex; gap: 16px; flex-wrap: wrap;">
  <span><strong style="color: #2C2C2C;">Long tail (24 more):</strong> xAI Grok · Qwen · Hugging Face · AWS Bedrock · Ollama Cloud · Azure Foundry · NVIDIA NIM · Fireworks · Z.AI · Kimi · OpenCode · Kilo Code · +15 more</span>
  <span><strong style="color: #2C2C2C;">Hard requirement:</strong> model context ≥ <strong>64,000 tokens</strong></span>
  <span><strong style="color: #2C2C2C;">Full list:</strong> <a href="https://hermes-agent.nousresearch.com/docs/integrations/providers" target="_blank" style="color: #FF6B35; font-weight: 600;">AI Providers</a></span>
</div>

---
layout: default
---

# How settings are stored

Hermes separates secrets from normal config. Two files, two purposes.

<div class="grid grid-cols-2 gap-4" style="margin-top: 22px;">
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 16px 18px;">
    <h3 style="margin: 0 0 8px; font-size: 17px; color: #2C2C2C;">
      <span style="display: inline-block; background: rgba(216, 85, 106, 0.12); color: #D8556A; border-radius: 999px; padding: 2px 9px; font-size: 10.5px; font-weight: 600; letter-spacing: 0.5px; margin-right: 6px;">SECRET</span>
      ~/.hermes/.env
    </h3>
    <p style="margin: 0 0 10px; color: #6B6B6B; font-size: 13px; line-height: 1.5;">API keys, OAuth tokens, anything sensitive. Never commit this file.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 6px; padding: 10px 12px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 11.5px; line-height: 1.6;">
      <div>OPENROUTER_API_KEY=sk-or-...</div>
      <div>ANTHROPIC_API_KEY=sk-ant-...</div>
    </div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 16px 18px;">
    <h3 style="margin: 0 0 8px; font-size: 17px; color: #2C2C2C;">
      <span style="display: inline-block; background: rgba(79, 168, 92, 0.12); color: #4FA85C; border-radius: 999px; padding: 2px 9px; font-size: 10.5px; font-weight: 600; letter-spacing: 0.5px; margin-right: 6px;">NON-SECRET</span>
      ~/.hermes/config.yaml
    </h3>
    <p style="margin: 0 0 10px; color: #6B6B6B; font-size: 13px; line-height: 1.5;">Model choice, terminal backend, enabled toolsets, MCP servers. Safe to inspect.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 6px; padding: 10px 12px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 11.5px; line-height: 1.6;">
      <div>model: anthropic/claude-opus-4.6</div>
      <div>terminal:</div>
      <div>&nbsp;&nbsp;backend: docker</div>
    </div>
  </div>
</div>

<div style="margin-top: 18px; padding: 12px 16px; background: #FFF8F4; border-radius: 10px; font-size: 13px;">
  <strong style="color: #2C2C2C;">Easiest way to set values correctly:</strong> use the CLI — it routes each value to the right file automatically.
  <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 6px; padding: 10px 12px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 12px; line-height: 1.6; margin-top: 8px;">
    <div><span style="color: #5EC4A8;">$</span> hermes config set model anthropic/claude-opus-4.6</div>
    <div><span style="color: #5EC4A8;">$</span> hermes config set terminal.backend docker</div>
    <div><span style="color: #5EC4A8;">$</span> hermes config set OPENROUTER_API_KEY sk-or-...</div>
  </div>
</div>

---
layout: default
---

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%); color: white; display: flex; flex-direction: column; justify-content: center; padding: 60px 80px;">

# Section 03
# <span style="color: white;">First chat</span>

<div style="margin-top: 20px; font-size: 18px; opacity: 0.92;">Start the interface, send a real prompt, watch the agent work.</div>

</div>

---
layout: default
---

# Start the CLI — pick your interface

Hermes ships with two terminals. Both share sessions, slash commands, and config — try each.

<div class="grid grid-cols-2 gap-4" style="margin-top: 22px;">
  <div style="background: #FFFFFF; border: 2px solid #FF6B35; border-radius: 12px; padding: 16px 18px; box-shadow: 0 4px 14px rgba(255, 107, 53, 0.12);">
    <div style="display: inline-block; background: #FF6B35; color: white; border-radius: 999px; padding: 3px 10px; font-size: 10.5px; font-weight: 700; letter-spacing: 0.6px;">RECOMMENDED</div>
    <h3 style="margin: 8px 0 4px; font-size: 17px; color: #2C2C2C;">TUI</h3>
    <p style="margin: 0 0 10px; color: #6B6B6B; font-size: 13px; line-height: 1.5;">Modern interface with modal overlays, mouse selection, non-blocking input.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 6px; padding: 8px 12px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 13px;"><span style="color: #5EC4A8;">$</span> hermes --tui</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 16px 18px;">
    <h3 style="margin: 0 0 4px; font-size: 17px; color: #2C2C2C;">Classic CLI</h3>
    <p style="margin: 0 0 10px; color: #6B6B6B; font-size: 13px; line-height: 1.5;">The original <code>prompt_toolkit</code> REPL. Lighter, fewer features, fully compatible.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 6px; padding: 8px 12px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 13px;"><span style="color: #5EC4A8;">$</span> hermes</div>
  </div>
</div>

<div style="margin-top: 22px;">
  <h3 style="color: #FF6B35; margin-top: 0;">What success looks like</h3>
  <div class="grid grid-cols-2 gap-3" style="margin-top: 10px;">
    <div style="display: flex; align-items: flex-start; gap: 10px;">
      <span style="display: inline-block; background: rgba(79, 168, 92, 0.12); color: #4FA85C; border-radius: 999px; padding: 2px 9px; font-size: 11px; font-weight: 700; flex-shrink: 0;">✓</span>
      <span style="font-size: 13px; color: #2C2C2C;">The banner shows your chosen model and provider</span>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 10px;">
      <span style="display: inline-block; background: rgba(79, 168, 92, 0.12); color: #4FA85C; border-radius: 999px; padding: 2px 9px; font-size: 11px; font-weight: 700; flex-shrink: 0;">✓</span>
      <span style="font-size: 13px; color: #2C2C2C;">Hermes replies without error</span>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 10px;">
      <span style="display: inline-block; background: rgba(79, 168, 92, 0.12); color: #4FA85C; border-radius: 999px; padding: 2px 9px; font-size: 11px; font-weight: 700; flex-shrink: 0;">✓</span>
      <span style="font-size: 13px; color: #2C2C2C;">It can use a tool when needed (terminal, file read, web search)</span>
    </div>
    <div style="display: flex; align-items: flex-start; gap: 10px;">
      <span style="display: inline-block; background: rgba(79, 168, 92, 0.12); color: #4FA85C; border-radius: 999px; padding: 2px 9px; font-size: 11px; font-weight: 700; flex-shrink: 0;">✓</span>
      <span style="font-size: 13px; color: #2C2C2C;">The conversation continues normally for more than one turn</span>
    </div>
  </div>
</div>

---
layout: default
---

# Three starter prompts

Use a prompt that's <strong>specific and easy to verify</strong>. The agent's answer is your smoke test.

<div style="margin-top: 18px;">
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-left: 4px solid #FF6B35; border-radius: 10px; padding: 14px 16px; margin-bottom: 10px;">
    <div style="font-size: 11px; color: #FF6B35; font-weight: 700; letter-spacing: 0.6px; text-transform: uppercase;">Repo · Read + summarise</div>
    <div style="font-size: 14.5px; color: #2C2C2C; margin-top: 4px; font-style: italic;">"Summarize this repo in 5 bullets and tell me what the main entrypoint is."</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-left: 4px solid #FF6B35; border-radius: 10px; padding: 14px 16px; margin-bottom: 10px;">
    <div style="font-size: 11px; color: #FF6B35; font-weight: 700; letter-spacing: 0.6px; text-transform: uppercase;">File system · Tool use</div>
    <div style="font-size: 14.5px; color: #2C2C2C; margin-top: 4px; font-style: italic;">"Check my current directory and tell me what looks like the main project file."</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-left: 4px solid #FF6B35; border-radius: 10px; padding: 14px 16px;">
    <div style="font-size: 11px; color: #FF6B35; font-weight: 700; letter-spacing: 0.6px; text-transform: uppercase;">Multi-step · Plan + act</div>
    <div style="font-size: 14.5px; color: #2C2C2C; margin-top: 4px; font-style: italic;">"Help me set up a clean GitHub PR workflow for this codebase."</div>
  </div>
</div>

<div style="margin-top: 16px; padding: 12px 16px; background: rgba(79, 168, 92, 0.08); border-left: 3px solid #4FA85C; border-radius: 6px; font-size: 13px;">
  <strong style="color: #4FA85C;">If that works, you're past the hardest part.</strong> Layer skills, MCP, cron, or a Telegram bot only after the base chat is stable.
</div>

---
layout: default
---

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%); color: white; display: flex; flex-direction: column; justify-content: center; padding: 60px 80px;">

# Section 04
# <span style="color: white;">Verify sessions</span>

<div style="margin-top: 20px; font-size: 18px; opacity: 0.92;">Before you juggle multiple setups or machines, make sure resume works.</div>

</div>

---
layout: default
---

# `hermes --continue` — the resume check

Before moving on, verify that the most recent session can be picked back up.

<div class="grid grid-cols-2 gap-6" style="margin-top: 22px;">
  <div>
    <h3 style="color: #FF6B35; margin-top: 0;">Run it</h3>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 10px; padding: 14px 16px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 13px; line-height: 1.6; box-shadow: 0 6px 20px rgba(0, 0, 0, 0.18);">
      <div><span style="color: #5EC4A8;">$</span> <span style="color: #FF8C42;">hermes --continue</span>    <span style="color: #888;"># full form</span></div>
      <div><span style="color: #5EC4A8;">$</span> <span style="color: #FF8C42;">hermes -c</span>            <span style="color: #888;"># short form</span></div>
    </div>
    <p style="font-size: 13px; color: #6B6B6B; margin-top: 12px;">That should bring you back to the session you just had — same conversation, same context, same files in scope.</p>
  </div>
  <div>
    <h3 style="color: #FF6B35; margin-top: 0;">If it can't find the session</h3>
    <ul style="font-size: 13px; line-height: 1.7; color: #2C2C2C;">
      <li>You may have <strong>switched profiles</strong>. Check with <code>hermes profile</code>.</li>
      <li>The session may have <strong>never saved</strong>. List with <code>hermes sessions list</code>.</li>
      <li>The profile's session dir may have been <strong>rotated or wiped</strong>.</li>
    </ul>
    <div style="background: #FFF8F4; border: 1px solid rgba(255, 107, 53, 0.25); border-radius: 10px; padding: 12px 14px; margin-top: 14px; font-size: 12.5px;">
      <strong style="color: #FF6B35;">Why this matters.</strong> Once you're juggling multiple setups, machines, or bot accounts, resume is the difference between "where was I" and "start over".
    </div>
  </div>
</div>

---
layout: default
---

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%); color: white; display: flex; flex-direction: column; justify-content: center; padding: 60px 80px;">

# Section 05
# <span style="color: white;">Key features</span>

<div style="margin-top: 20px; font-size: 18px; opacity: 0.92;">Terminal, slash commands, multi-line input, interrupt — the four you'll use daily.</div>

</div>

---
layout: default
---

# Key features — terminal, slash, multi-line, interrupt

<div class="grid grid-cols-2 gap-4" style="margin-top: 18px;">
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 14px 16px;">
    <h3 style="margin: 0 0 6px; font-size: 15px; color: #FF6B35;">Use the terminal</h3>
    <p style="margin: 0 0 8px; color: #6B6B6B; font-size: 12.5px; line-height: 1.45;">The agent runs commands on your behalf and shows results.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 6px; padding: 8px 12px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 11.5px; line-height: 1.55;">❯ What's my disk usage? Show the top 5 largest directories.</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 14px 16px;">
    <h3 style="margin: 0 0 6px; font-size: 15px; color: #FF6B35;">Slash commands</h3>
    <p style="margin: 0 0 8px; color: #6B6B6B; font-size: 12.5px; line-height: 1.45;">Type <code>/</code> to see an autocomplete dropdown of all commands.</p>
    <div style="font-size: 11.5px; line-height: 1.65; color: #2C2C2C;">
      <div><code>/help</code> — show all commands</div>
      <div><code>/tools</code> — list available tools</div>
      <div><code>/model</code> — switch models interactively</div>
      <div><code>/personality pirate</code> — try a fun persona</div>
      <div><code>/save</code> — save the conversation</div>
    </div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 14px 16px;">
    <h3 style="margin: 0 0 6px; font-size: 15px; color: #FF6B35;">Multi-line input</h3>
    <p style="margin: 0 0 8px; color: #6B6B6B; font-size: 12.5px; line-height: 1.45;">Add a newline without sending the prompt.</p>
    <div style="font-size: 11.5px; line-height: 1.65; color: #2C2C2C;">
      <div><code>Alt+Enter</code> — works everywhere</div>
      <div><code>Ctrl+J</code> — works everywhere</div>
      <div><code>Shift+Enter</code> — needs Kitty protocol (Kitty / foot / WezTerm / Ghostty; iTerm2 / Alacritty / VS Code after enabling it)</div>
    </div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 14px 16px;">
    <h3 style="margin: 0 0 6px; font-size: 15px; color: #FF6B35;">Interrupt the agent</h3>
    <p style="margin: 0 0 8px; color: #6B6B6B; font-size: 12.5px; line-height: 1.45;">If the agent is taking too long, just type a new message and press Enter — it cancels the current task and switches to your new instructions.</p>
    <div style="font-size: 11.5px; color: #6B6B6B;"><code>Ctrl+C</code> also works as a hard cancel.</div>
  </div>
</div>

---
layout: default
---

<div style="position: absolute; inset: 0; background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%); color: white; display: flex; flex-direction: column; justify-content: center; padding: 60px 80px;">

# Section 06
# <span style="color: white;">Add the next layer</span>

<div style="margin-top: 20px; font-size: 18px; opacity: 0.92;">Bots, automation, sandbox, voice, skills, MCP, ACP — pick what you need, skip the rest.</div>

</div>

---
layout: default
---

# The next layer — pick what you need

<div class="grid grid-cols-3 gap-3" style="margin-top: 12px;">
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 10px; padding: 10px 12px;">
    <h3 style="margin: 0 0 4px; font-size: 13px; color: #FF6B35;">Bot / shared assistant</h3>
    <p style="margin: 0 0 6px; color: #6B6B6B; font-size: 11px; line-height: 1.35;">Connect a messaging platform.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 5px; padding: 6px 10px; font-family: 'JetBrains Mono', monospace; font-size: 10.5px;"><span style="color: #5EC4A8;">$</span> hermes gateway setup</div>
    <p style="margin: 6px 0 0; font-size: 10px; color: #6B6B6B;">Telegram · Discord · Slack · WhatsApp · Signal · Email · Teams</p>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 10px; padding: 10px 12px;">
    <h3 style="margin: 0 0 4px; font-size: 13px; color: #FF6B35;">Sandboxed terminal</h3>
    <p style="margin: 0 0 6px; color: #6B6B6B; font-size: 11px; line-height: 1.35;">Run the agent in Docker or remotely.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 5px; padding: 6px 10px; font-family: 'JetBrains Mono', monospace; font-size: 10.5px;"><span style="color: #5EC4A8;">$</span> config set terminal.backend docker</div>
    <p style="margin: 6px 0 0; font-size: 10px; color: #6B6B6B;">Or <code style="font-size: 10px;">terminal.backend ssh</code> for remote.</p>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 10px; padding: 10px 12px;">
    <h3 style="margin: 0 0 4px; font-size: 13px; color: #FF6B35;">Voice mode</h3>
    <p style="margin: 0 0 6px; color: #6B6B6B; font-size: 11px; line-height: 1.35;">Local speech-to-text via faster-whisper.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 5px; padding: 6px 10px; font-family: 'JetBrains Mono', monospace; font-size: 10.5px;"><span style="color: #5EC4A8;">$</span> uv pip install -e ".[voice]"</div>
    <p style="margin: 6px 0 0; font-size: 10px; color: #6B6B6B;">Then <code style="font-size: 10px;">/voice on</code>. <code style="font-size: 10px;">Ctrl+B</code> records.</p>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 10px; padding: 10px 12px;">
    <h3 style="margin: 0 0 4px; font-size: 13px; color: #FF6B35;">Skills</h3>
    <p style="margin: 0 0 6px; color: #6B6B6B; font-size: 11px; line-height: 1.35;">Reusable SKILL.md instruction packs.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 5px; padding: 6px 10px; font-family: 'JetBrains Mono', monospace; font-size: 10.5px;"><span style="color: #5EC4A8;">$</span> hermes skills browse</div>
    <p style="margin: 6px 0 0; font-size: 10px; color: #6B6B6B;">Install: <code style="font-size: 10px;">openai/skills/k8s</code> · Use: <code style="font-size: 10px;">/k8s</code></p>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 10px; padding: 10px 12px;">
    <h3 style="margin: 0 0 4px; font-size: 13px; color: #FF6B35;">MCP servers</h3>
    <p style="margin: 0 0 6px; color: #6B6B6B; font-size: 11px; line-height: 1.35;">Third-party tools via MCP.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 5px; padding: 5px 10px; font-family: 'JetBrains Mono', monospace; font-size: 10px; line-height: 1.4;"><span style="color: #888;"># config.yaml</span><br><span style="color: #FF8C42;">mcp_servers:</span><br>&nbsp;&nbsp;github:&nbsp; command: npx</div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 10px; padding: 10px 12px;">
    <h3 style="margin: 0 0 4px; font-size: 13px; color: #FF6B35;">Editor (ACP)</h3>
    <p style="margin: 0 0 6px; color: #6B6B6B; font-size: 11px; line-height: 1.35;">Hermes from inside an IDE.</p>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 5px; padding: 6px 10px; font-family: 'JetBrains Mono', monospace; font-size: 10.5px;"><span style="color: #5EC4A8;">$</span> hermes acp</div>
    <p style="margin: 6px 0 0; font-size: 10px; color: #6B6B6B;">Included in the standard curl installer.</p>
  </div>
</div>

<div style="margin-top: 10px; padding: 8px 12px; background: rgba(255, 107, 53, 0.08); border-left: 3px solid #FF6B35; border-radius: 6px; font-size: 12px;">
  <strong style="color: #FF6B35;">Order matters.</strong> Add only what you need. Cron, routing, and multi-provider fallback all wait until the base chat is stable.
</div>

---
layout: default
---

# Common Failure Modes + Recovery Toolkit

These are the problems that waste the most time. When something feels off, run the recovery steps in order.

<div class="grid grid-cols-2 gap-4" style="margin-top: 18px;">
  <div>
    <h3 style="color: #FF6B35; margin-top: 0;">Symptom → Fix</h3>
    <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 12px 14px; font-size: 12px; line-height: 1.6;">
      <div style="margin-bottom: 6px;"><span style="display: inline-block; background: rgba(216, 85, 106, 0.12); color: #D8556A; border-radius: 999px; padding: 1px 7px; font-size: 10px; font-weight: 700; margin-right: 6px;">EMPTY REPLIES</span>Provider auth or model selection is wrong. Run <code>hermes model</code> and confirm provider, model, auth.</div>
      <div style="margin-bottom: 6px;"><span style="display: inline-block; background: rgba(216, 85, 106, 0.12); color: #D8556A; border-radius: 999px; padding: 1px 7px; font-size: 10px; font-weight: 700; margin-right: 6px;">GARBAGE OUTPUT</span>Custom endpoint — wrong base URL, model name, or not actually OpenAI-compatible. Verify in a separate client first.</div>
      <div style="margin-bottom: 6px;"><span style="display: inline-block; background: rgba(216, 85, 106, 0.12); color: #D8556A; border-radius: 999px; padding: 1px 7px; font-size: 10px; font-weight: 700; margin-right: 6px;">GATEWAY DEAD</span>Bot token, allowlist, or platform setup is incomplete. Re-run <code>hermes gateway setup</code>; check <code>hermes gateway status</code>.</div>
      <div style="margin-bottom: 6px;"><span style="display: inline-block; background: rgba(216, 85, 106, 0.12); color: #D8556A; border-radius: 999px; padding: 1px 7px; font-size: 10px; font-weight: 700; margin-right: 6px;">NO OLD SESSION</span>Switched profiles or session never saved. <code>hermes sessions list</code>; confirm profile.</div>
      <div style="margin-bottom: 6px;"><span style="display: inline-block; background: rgba(216, 85, 106, 0.12); color: #D8556A; border-radius: 999px; padding: 1px 7px; font-size: 10px; font-weight: 700; margin-right: 6px;">ODD FALLBACK</span>Provider routing too aggressive. Keep routing off until base provider is stable.</div>
      <div><span style="display: inline-block; background: rgba(216, 85, 106, 0.12); color: #D8556A; border-radius: 999px; padding: 1px 7px; font-size: 10px; font-weight: 700; margin-right: 6px;">DOCTOR WARNS</span>Config values missing or stale. Fix config, retest a plain chat before adding features.</div>
    </div>
  </div>
  <div>
    <h3 style="color: #FF6B35; margin-top: 0;">When something feels off</h3>
    <div style="background: #1E1E1E; color: #E6E6E6; border-radius: 10px; padding: 12px 14px; font-family: 'JetBrains Mono', 'Fira Code', Menlo, Consolas, monospace; font-size: 12.5px; line-height: 1.7; box-shadow: 0 6px 20px rgba(0, 0, 0, 0.18);">
      <div><span style="color: #888;">1.</span> <span style="color: #FF8C42;">hermes doctor</span>           <span style="color: #888;"># diagnose config</span></div>
      <div><span style="color: #888;">2.</span> <span style="color: #FF8C42;">hermes model</span>            <span style="color: #888;"># re-confirm provider</span></div>
      <div><span style="color: #888;">3.</span> <span style="color: #FF8C42;">hermes setup</span>            <span style="color: #888;"># re-run the wizard</span></div>
      <div><span style="color: #888;">4.</span> <span style="color: #FF8C42;">hermes sessions list</span>    <span style="color: #888;"># check saved sessions</span></div>
      <div><span style="color: #888;">5.</span> <span style="color: #FF8C42;">hermes --continue</span>       <span style="color: #888;"># resume last session</span></div>
      <div><span style="color: #888;">6.</span> <span style="color: #FF8C42;">hermes gateway status</span>   <span style="color: #888;"># check bot platform</span></div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin-top: 10px;">That sequence gets you from "broken vibes" back to a known state fast. Use it before adding any new feature.</p>
  </div>
</div>

---
layout: default
---

# Quick Reference + Next Steps · Q&A

Memorise these eight commands. Everything else lives in the docs.

<div class="grid grid-cols-2 gap-4" style="margin-top: 18px;">
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 16px 18px;">
    <h3 style="margin: 0 0 8px; font-size: 17px; color: #FF6B35;">Quick reference</h3>
    <div style="font-size: 13px; line-height: 1.85; color: #2C2C2C;">
      <div><code style="background: #1E1E1E; color: #E6E6E6; padding: 2px 7px; border-radius: 4px; font-family: 'JetBrains Mono', monospace;">hermes</code> <span style="color: #6B6B6B; font-size: 12px; margin-left: 8px;">— start chatting</span></div>
      <div><code style="background: #1E1E1E; color: #E6E6E6; padding: 2px 7px; border-radius: 4px; font-family: 'JetBrains Mono', monospace;">hermes model</code> <span style="color: #6B6B6B; font-size: 12px; margin-left: 8px;">— choose provider + model</span></div>
      <div><code style="background: #1E1E1E; color: #E6E6E6; padding: 2px 7px; border-radius: 4px; font-family: 'JetBrains Mono', monospace;">hermes tools</code> <span style="color: #6B6B6B; font-size: 12px; margin-left: 8px;">— configure tools per platform</span></div>
      <div><code style="background: #1E1E1E; color: #E6E6E6; padding: 2px 7px; border-radius: 4px; font-family: 'JetBrains Mono', monospace;">hermes setup</code> <span style="color: #6B6B6B; font-size: 12px; margin-left: 8px;">— full setup wizard</span></div>
      <div><code style="background: #1E1E1E; color: #E6E6E6; padding: 2px 7px; border-radius: 4px; font-family: 'JetBrains Mono', monospace;">hermes doctor</code> <span style="color: #6B6B6B; font-size: 12px; margin-left: 8px;">— diagnose issues</span></div>
      <div><code style="background: #1E1E1E; color: #E6E6E6; padding: 2px 7px; border-radius: 4px; font-family: 'JetBrains Mono', monospace;">hermes update</code> <span style="color: #6B6B6B; font-size: 12px; margin-left: 8px;">— upgrade to latest</span></div>
      <div><code style="background: #1E1E1E; color: #E6E6E6; padding: 2px 7px; border-radius: 4px; font-family: 'JetBrains Mono', monospace;">hermes gateway</code> <span style="color: #6B6B6B; font-size: 12px; margin-left: 8px;">— start messaging gateway</span></div>
      <div><code style="background: #1E1E1E; color: #E6E6E6; padding: 2px 7px; border-radius: 4px; font-family: 'JetBrains Mono', monospace;">hermes --continue</code> <span style="color: #6B6B6B; font-size: 12px; margin-left: 8px;">— resume last session</span></div>
    </div>
  </div>
  <div style="background: #FFFFFF; border: 1px solid #ECECEC; border-radius: 12px; padding: 16px 18px;">
    <h3 style="margin: 0 0 8px; font-size: 17px; color: #FF6B35;">Where to go next</h3>
    <ul style="margin: 0; padding-left: 18px; font-size: 13px; line-height: 1.7; color: #2C2C2C;">
      <li><a href="https://hermes-agent.nousresearch.com/docs/user-guide/cli" target="_blank" style="color: #FF6B35; font-weight: 600;">CLI Guide</a> — master the terminal interface</li>
      <li><a href="https://hermes-agent.nousresearch.com/docs/user-guide/configuration" target="_blank" style="color: #FF6B35; font-weight: 600;">Configuration</a> — customise your setup</li>
      <li><a href="https://hermes-agent.nousresearch.com/docs/user-guide/messaging/" target="_blank" style="color: #FF6B35; font-weight: 600;">Messaging Gateway</a> — Telegram, Discord, Slack, WhatsApp, Signal, Email, Teams, more</li>
      <li><a href="https://hermes-agent.nousresearch.com/docs/user-guide/features/tools" target="_blank" style="color: #FF6B35; font-weight: 600;">Tools &amp; Toolsets</a> — full capability catalog</li>
      <li><a href="https://hermes-agent.nousresearch.com/docs/integrations/providers" target="_blank" style="color: #FF6B35; font-weight: 600;">AI Providers</a> — every supported provider, setup steps, env vars</li>
      <li><a href="https://hermes-agent.nousresearch.com/docs/user-guide/features/skills" target="_blank" style="color: #FF6B35; font-weight: 600;">Skills System</a> — write your own, browse the hub</li>
    </ul>
    <div style="margin-top: 14px; text-align: center; font-size: 14px; color: #6B6B6B; font-weight: 600;">Thanks for reading. Now go install it.</div>
  </div>
</div>