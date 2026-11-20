# F3 — OpenClaw coding agents ane ena models: research (Gujlish)

> **Shu che aa file:** Q-43 mate research. OpenClaw je coding-agent CLI support kare che, darek ma **kaya models** che, kayu **free** che, ane darek model **3 level** ma kya aave.
> **Taarikh:** 15 October 2026. Mahiti official docs, live model APIs (Kilo, OpenCode, OpenRouter) ane benchmark sites (BenchLM, Vals) mathi.
> **Haju baki:** Discord / Reddit par user reviews (section 8) — e pachi j aakhri nirnay.
> **Round 67:** bandh thayela coding agent ane models aa file mathi **puri rite kadhya** (iFlow CLI, ane bandh / deprecated models). Local LLM support karta agents ni **alag yaadi** — section 5.
> Je vaat confirm na thai e **(unverified)** lakhi che. Koi model ke kimat potani rite umeri nathi.

---

## 0. Sauthi mahatvani vaat (pehla vancho)

| # | Vaat | Asar |
|---|---|---|
| 1 | **Gemini CLI no free plan 18 June 2026 thi bandh** — free user have "Antigravity CLI" par; Gemini CLI fakt Code Assist license ke API key thi | Gemini have "free agent" nathi (API key free tier: fakt Flash, 250 / divas — unverified) |
| 2 | **Qwen Code no free (Qwen OAuth) plan 15 April 2026 thi bandh** | Qwen Code have free nathi — fakt OpenRouter free, ke local |
| 3 | **Trae CLI** — third-party page kahe che fakt **Enterprise** account mate; official CLI docs khulya nahi | Unverified — confirm joie |
| 4 | **Mux nu naam have Xum** (Coder) — command haju `mux acp` | Kai nahi |
| 5 | OpenClaw (v2026.10.3, 13 Oct) ni registry ma **5 nava agent** — `openclaw`, `devin`, `fx`, `junie`, `antigravity`; aapna 21 mathi koi nikadyu nathi | Navo nirnay joie ke umervu ke nahi |
| 6 | **Sauthi vadhare free models: Kilo Code (13), OpenCode Zen (~10), OpenRouter (15)** — badha "limited time" free; ghana free models prompts ne training mate vapre | Easy task mate mukhya free pool |
| 7 | Local LLM sidhu jodai — **13 agents** (puri yaadi section 5) | F5 ni local-LLM script mate saro |

---

## 0.1 OpenClaw support — confirm (15 Oct 2026)

Be official jagya sathe melavyu: OpenClaw setup page (`docs.openclaw.ai/tools/acp-agents-setup`, 22 id) ane acpx registry (`github.com/openclaw/acpx/blob/main/docs/agents.md`, 26 id).

| Aa file na 20 agents | OpenClaw setup page | acpx registry | Note |
|---|---|---|---|
| claude, copilot, cursor, droid, fast-agent, gemini, grok-build, kilocode, kimi, kiro, mcode, mux, opencode, pi, pool, qoder, qwen, trae, zeroclaw | ✅ | ✅ | — |
| codex | ✅ | ✅ | OpenClaw kahe: ACP ni jarur na hoy to Codex nu potanu "app-server" rasto vadhare saru |
| copilot (vadhare) | — | — | ACP thi model pasand karva Copilot CLI **1.0.86 ke navu** joie |
| cursor (vadhare) | — | — | Install ma `agent acp` hoy to acpx config ma command badalvo |

- **iflow** OpenClaw na page par haju che, pan iFlow CLI pote bandh thai gayu — etle aa file ma nathi (20 agents).
- **OpenClaw ni list ma che, aa file ma nathi:** `openclaw` (OpenClaw no potano bridge — coding agent nathi); fakt acpx registry ma: `antigravity`, `devin`, `fx`, `junie` (setup page par nathi).
- **Model vishe:** OpenClaw **agent** ne support kare che. Agent ni andar **kayu model** OpenClaw pasand kari shake e agent na ACP adapter par aadhar rakhe — darek agent mate nano test baki (implementation.md, appendix A).

## 1. 3 level no arth

| Level | Arth | Kevu kaam |
|---|---|---|
| **LOW + free** | Nanu / jaldi model, free | Text, spelling, style, nano UI badlav |
| **MEDIUM + free / premium** | Saru coding model — free ke paid | Saman bugfix, ek-be file nu kaam |
| **HIGH + premium** | Sauthi saru (frontier) coding model, paid | Moto feature, ghani files, auth / payment / data |

**Benchmark vishe chetavni:** SWE-bench Verified (SWE-V) ma top models ~96% par pahonchya — have bahu pharak nathi batavtu; SWE-bench Pro (SWE-Pro) ane Terminal-Bench vadhare kaam na. Ghana 2026 na nava models (Opus 5.5, GPT-6.x, Gemini 4 Argon, Kimi K3) na chokkas aankda nathi — tya level **vendor ni positioning ane kimat** parthi (unverified). Aankda fakt disha mate.

---

## 2. Agent — ek nazar ma (20)

| # | Agent (OpenClaw id) | Free plan? | Free models | Potani key / local LLM | Status |
|---|---|---|---|---|---|
| 1 | Claude Code (`claude`) | **Na** (Pro $20 thi) | — | Anthropic key; gateway thi biju | ✅ |
| 2 | Codex CLI (`codex`) | Free / Go: GPT-6 Luna fakt desktop app ma (CLI unverified); Plus $20 | Local gpt-oss (Ollama) | Haa — key, Ollama, LM Studio | ✅ |
| 3 | GitHub Copilot CLI (`copilot`) | Free: fakt "Auto" model, nani limit (CLI unverified); Pro $10 | Auto | Haa — key, Ollama | ✅ |
| 4 | Cursor CLI (`cursor`) | Free: limited requests (unverified CLI mate); plan naam alag-alag pages par | Auto | Key (fakt chat models; CLI unverified); local — documented nathi | ✅ |
| 5 | Factory Droid (`droid`) | **Na** (Pro $20) — pan paid plan par **Droid Core free open models** | MiniMax M3, Inkling, GLM, Qwen3.8 Max, Kimi K3 … | Haa — key, Ollama, LM Studio | ✅ |
| 6 | fast-agent (`fast-agent`) | Potana models nathi | OpenRouter free, local | Haa — badhu | ✅ |
| 7 | Gemini CLI (`gemini`) | **Na** (18 June 2026 thi); API key free tier fakt Flash (unverified) | Gemini Flash (API free), local Gemma 4 | Gemini key; local Gemma | ⚠️ free bandh |
| 8 | Grok Build (`grok-build`) | **Na** (SuperGrok $30); API nava account ne $25 credit (unverified) | — | Haa — key, custom base_url, local | ✅ (beta) |
| 9 | Kilo Code (`kilocode`) | **Haa** — free models login vagar pan (200 request / kalak / IP) | **13** | Haa — key, Ollama, LM Studio, OpenAI-compatible | ✅ mukhya free |
| 10 | Kimi Code (`kimi`) | Official page par free nathi (Plus ¥99 thi) | — | Kimi key; Anthropic / OpenAI / Google key | ✅ |
| 11 | Kiro CLI (`kiro`) | **Haa** — 50 credit / mahino | Qwen3 Coder Next, DeepSeek 3.2, MiniMax M2.1 / M2.5, GLM-5, Sonnet 4.5 | Na (documented nathi) | ✅ |
| 12 | MiniMax Code (`mcode`) | Na (Go $22 thi) | — | Haa — custom provider; local (unverified) | ✅ |
| 13 | Mux / Xum (`mux`) | Software free; models potani key thi | Ollama local | Haa — 11 providers, Ollama | ✅ (naam Xum) |
| 14 | OpenCode (`opencode`) | **Haa** — Zen free models; Go $10 | **~10** | Haa — key, Ollama, LM Studio, llama.cpp | ✅ mukhya free |
| 15 | Pi (`pi`) | Potana models nathi | OpenCode Zen free, OpenRouter free, NVIDIA NIM | Haa — badhu | ✅ |
| 16 | Poolside Pool (`pool`) | **Haa** — free login key ("limited time") | Laguna XS 2.1, Laguna M.1 | OpenRouter key; Ollama | ✅ |
| 17 | Qoder CLI (`qoder`) | Free: basic models, limited messages; Pro $20 | Basic / Lite | Custom models (Alibaba, DeepSeek, Kimi …); local nahi | ✅ |
| 18 | Qwen Code (`qwen`) | **Na** (15 Apr 2026 thi) | OpenRouter free, local | Haa — key, Ollama, vLLM | ⚠️ free bandh |
| 19 | Trae CLI (`trae`) | Free: Auto, limited (CLI Enterprise-only — unverified) | Auto | Config thi (unverified) | ⚠️ unverified |
| 20 | ZeroClaw (`zeroclaw`) | Potana models nathi | Ollama local | Haa — ~20–30 providers | ✅ |

---

## 3. Free models — mukhya yaadi (easy task mate)

> Aa j mukhya pool. "Limited time" — badlay shake; darek release pehla live list farithi joie.

### 3.1 Kilo Code (Kilo Gateway, live API 14 Oct 2026) — 13 free

| Model | Kon nu | Level | Kem |
|---|---|---|---|
| `kilo-auto/free` (router) | Kilo — free models ma thi pasand kare | MEDIUM + free | Kilo pote "limited capability" kahe |
| Inkling Small | Thinking Machines | MEDIUM + free | SWE-V 80.2%, SWE-Pro 55.9% |
| Dots 3 Note Preview | Dots Studio | MEDIUM + free | SWE-V 78.4%, SWE-Pro 61% |
| Nemotron 3 Ultra | NVIDIA | MEDIUM + free | SWE-V 71.9% (trial use) |
| Laguna S 2.1 | Poolside | MEDIUM + free | SWE-Pro 59.4% |
| Step 5 Preview | StepFun | MEDIUM + free (kadach HIGH) | Terminal-Bench 2.1 85.0%; free fakt thoda divas (unverified) |
| Glyph Cluster (stealth) | ajanyu | MEDIUM + free (unverified) | Aankda nathi |
| Laguna XS 2.1 | Poolside | LOW + free | SWE-V 70.9% |
| Nemotron 3 Super | NVIDIA | LOW + free | SWE-V 60.5% |
| Nemotron 3.5 Lightning | NVIDIA | LOW + free | SWE-V 52.8% |
| North Mini Code | Cohere | LOW + free | Aankda nathi |
| Nemotron 3 Nano Omni | NVIDIA | LOW + free | Coding mate nahi |
| LFM 2.5 2.6B | Liquid AI | LOW + free | Bahu nanu |

(Nemotron 3.5 Content Safety ane `openrouter/free` pan free che — pehlu coding model nathi, bijo random pasand kare.)

### 3.2 OpenCode Zen — ~10 free (badha "limited time")

| Model | Level | Kem |
|---|---|---|
| Step 5 Preview Free | MEDIUM + free | Terminal-Bench 2.1 85.0%; Go plan par unlimited |
| Muse Spark 1.3 / 1.2 Contributor Free (Meta) | MEDIUM + free | Juna version SWE-Pro 61.5%; **prompts Meta training mate** |
| MiMo V2.6 Flash Free (Xiaomi) | MEDIUM + free (unverified) | Juna version SWE-V 73.4% |
| Big Pickle (stealth) | MEDIUM + free (unverified) | Aankda nathi |
| LongCat 2.5 Preview Free (Meituan) | MEDIUM + free (unverified) | Aankda nathi |
| Cat Jam Free, Space Bunny Free (stealth) | MEDIUM + free (unverified) | Aankda nathi |
| Nemotron 3.5 Lightning Free | LOW + free | SWE-V 52.8% |
| Jev 1.13 Free | unverified | Mahiti nathi |

### 3.3 OpenRouter `:free` — 15 (Pi, fast-agent, Qwen, Pool, Mux, ZeroClaw thi vapray)

Limit: dar minute 20; divas na 50 ($10 thi ochha credit) ke 1,000 ($10+).
Kilo vala j models + **Inkling** (MEDIUM, SWE-V 77.6%), **Gemma 4 26B / 31B** (LOW).

### 3.4 Bija free

| Kya | Free models | Sharat |
|---|---|---|
| Poolside Pool | Laguna M.1 (MEDIUM, SWE-V 74.6%), Laguna XS 2.1 (LOW) | Free login, "limited time" |
| Factory Droid — Droid Core | MiniMax M3 (MEDIUM, 80.5%), Inkling (77.6%), Mistral Medium 3.5 (77.6%), Nemotron 3 Ultra, GLM-5.2 / 5.3, Qwen3.8 Max, Kimi K3 (MEDIUM); GLM-5.3 Flash, DeepSeek V4.1 Flash (LOW) | **Paid plan joie** — usage puru thay pachi free |
| Kiro | Qwen3 Coder Next (LOW), MiniMax M2.1 (LOW), DeepSeek 3.2, MiniMax M2.5, GLM-5, Sonnet 4.5 (MEDIUM) | 50 credit / mahino, rate-limited |
| Codex | gpt-oss 120B / 20B (LOW, SWE-V 62.4% / 60.7%) | Local Ollama / LM Studio |
| Gemini | Gemini 2.5 Flash / Flash-Lite, 3 Flash (unverified) | API key free tier |

---

## 4. Darek agent na models — 3 level ma

> Kimat = 1M tokens dith input / output (jya malyu). Paid plan na models plan ni limit ma.

### 4.1 Claude Code
| Level | Models |
|---|---|
| HIGH + premium | Fable 5.1 ($10/$50; Max / Team Premium), Fable 5 (SWE-V 95%), **Opus 5.5 (default, $4/$20; SWE-Pro 89.9% — unverified)**, Opus 5 (SWE-V 96%), Opus 4.8 (88.6%) |
| MEDIUM + premium | Sonnet 5.5 ($2/$10), Sonnet 5 (85.2%), Sonnet 4.6 (79.6%) |
| LOW (paid) | Haiku 5.5 ($0.10/$0.50), Haiku 4.5 (73.3%) |

### 4.2 Codex CLI
| Level | Models |
|---|---|
| HIGH + premium | **GPT-6.1 Sol (recommended)**, GPT-6 Sol, GPT-6 Astra (5x kimat), GPT-5.6 Sol (SWE-V 96.2%) |
| MEDIUM + premium | GPT-5.6 Terra |
| LOW | GPT-6 Luna (Free plan — fakt desktop app; CLI mate Plus), GPT-5.6 Luna; **gpt-oss local = LOW + free** |

### 4.3 GitHub Copilot CLI (darek model AI credits kape)
| Level | Models |
|---|---|
| HIGH + premium (Pro+ $39 thi) | Opus 5.5, Opus 5, Opus 4.8, Fable 5 / 5.1, GPT-5.5, GPT-5.6 Sol, GPT-6 Sol / 6.1 Sol / Astra, Gemini 4 Argon |
| MEDIUM (Pro $10) | GPT-5.3-Codex (SWE-V 85%), GPT-5.4, GPT-5.6 Terra, Sonnet 5.5 / 5 / 4.6, Grok 4.5–4.7, Kimi K3 |
| LOW | **Auto (Free plan) = LOW + free**; GPT-5 mini, GPT-6 Luna, GPT-5.6 Luna, GPT-5.4 mini / nano, Haiku 4.5 / 5.5, Gemini 3.7 / 3.8 Flash, MAI-Code-1.1-Flash |

### 4.4 Cursor CLI
| Level | Models |
|---|---|
| HIGH + premium | Opus 5.5 / 5 / 4.8, Fable 5 / 5.1, GPT-5.5, GPT-5.6 Sol |
| MEDIUM | Composer 2.5 (Cursor nu, Terminal-Bench 2.0 69.3%), Grok 4.5–4.7, GPT-5.3 Codex, GPT-5.4, GPT-5.6 Terra, Sonnet 5.5 / 5 / 4.6, Gemini 3.1 Pro / 4 Argon, GLM 5.3, Kimi K3, Muse Spark 1.3 |
| LOW | **Auto (Free) = LOW + free (unverified)**; GPT-5.6 Luna, GPT-5.4 Nano, Haiku 5.5, Gemini Flash, GLM 5.3 Flash |
| Note | GPT-6.x Cursor ni list ma nathi dekhata (unverified) |

### 4.5 Factory Droid
| Level | Models |
|---|---|
| HIGH + premium | GPT-6.1 Sol / 6 Sol, Opus 5.5 / 5 / 4.8, Fable 5 / 5.1, GPT-6 Astra, GPT-5.5, GPT-5.6 Sol |
| MEDIUM | Sonnet 5.5 / 5 / 4.6, GPT-5.6 Terra, GPT-5.4, GPT-5.3-Codex, Gemini 3.1 Pro, Grok 4.5–4.7; **Droid Core free: MiniMax M3, Inkling, Mistral Medium 3.5 / Large 4, Nemotron 3 Ultra, GLM-5.2 / 5.3, Qwen3.8 Max, Kimi K3** |
| LOW | GPT-6 Luna, GPT-5.6 Luna, Haiku 5.5 / 4.5, GPT-5.4 Mini, Gemini Flash; **Droid Core free: GLM-5.3 Flash, DeepSeek V4.1 Flash** |

### 4.6 Gemini CLI
| Level | Models |
|---|---|
| HIGH + premium | Auto (Gemini 3), Gemini 3.1 Pro Preview (SWE-V 80.6%), Gemini 3 Pro Preview |
| MEDIUM | Gemini 3 Flash Preview (SWE-V 78%; API free tier — unverified), Gemini 2.5 Pro |
| LOW + free | Gemini 2.5 Flash / Flash-Lite (API free tier), **Gemma 4 local** |

### 4.7 Grok Build
| Level | Models |
|---|---|
| HIGH + premium | Grok 4.7 (default, $2/$6), Grok 4.6, Grok 4.5 (SWE-V 86.6% Vals, SWE-Pro 64.7%) |
| MEDIUM + premium | Grok Build 0.1 ($1/$2, jaldi), Grok 4.3 / 4.20 (unverified) |
| LOW + free | Custom / local model config thi |

### 4.8 Kilo Code — free: section 3.1. Paid (gateway, provider ni j kimat)
| Level | Models |
|---|---|
| HIGH + premium | `kilo-auto/frontier`, Opus 5.5, GPT-6.1 Sol, Kimi K3 |
| MEDIUM + premium | DeepSeek V4.1 Flash ($0.30/$1.20), GLM 5.3 Flash, `kilo-auto/balanced` / `efficient` |
| Baki | 394 models gateway par, ke potani key / local |

### 4.9 Kimi Code
| Level | Models |
|---|---|
| HIGH + premium | Kimi K3 (Terminal-Bench 2.1 88.3% — vendor) |
| MEDIUM | Kimi K2.7 Code (`kimi-for-coding`), K2.7 Code HighSpeed |

### 4.10 Kiro (credit multiplier)
| Level | Models |
|---|---|
| HIGH + premium | Opus 5.5 / 5 / 4.5–4.8, Sonnet 5 / 5.5, Fable 5.1 Preview (Enterprise), GPT-5.6 Sol / Terra |
| MEDIUM | **Free: Sonnet 4.5, DeepSeek 3.2, MiniMax M2.5, GLM-5, Auto**; paid: Sonnet 4.6 |
| LOW | **Free: Qwen3 Coder Next, MiniMax M2.1**; paid: Haiku 4.5, GPT-5.6 Luna |

### 4.11 MiniMax Code
| Level | Models |
|---|---|
| HIGH + premium | MiniMax-M3 (SWE-Pro 59.0%, Terminal-Bench 2.1 66.0%) |
| MEDIUM + premium | MiniMax-M3.1-Flash-Preview, MiniMax-M2.7 |

### 4.12 Mux / Xum (potani key)
| Level | Models |
|---|---|
| HIGH + premium | Opus 5.5 (default), Mythos 5.1, Fable 5.1, GPT-6.1 Sol, Gemini 4 Argon, DeepSeek V4 Pro, Kimi K3 |
| MEDIUM | Sonnet 5.5, Gemini 3.1 Pro, Grok 4.7, GPT-6 Luna / Astra (unverified) |
| LOW | Haiku 5.5, Gemini 3.8 Flash, DeepSeek V4 Flash, GLM 5.3 Flash; **Ollama local = LOW + free** |

### 4.13 OpenCode — free: section 3.2. Paid (Zen / Go)
| Level | Models |
|---|---|
| HIGH + premium | Opus 5.5 ($4/$20), Sonnet 5.5 (SWE-Pro 81.3%), Fable 5.1, GPT 6.1 Sol / 6 Sol / 5.6 Sol, Qwen3.8 Max (SWE-Pro 67.7%), Kimi K3, Gemini 4 Argon |
| MEDIUM + premium | GLM 5.3, Kimi K2.7 Code, MiniMax M3 (SWE-V 80.5%), DeepSeek V4.1 Flash, Qwen3.7 Plus (77.7%) |
| LOW | GLM 5.3 Flash, Qwen3.8 Flash, GPT 6 Luna, Haiku 5.5 (sasta) |

### 4.14 Pi ane fast-agent (potana models nathi)
- **Free:** OpenCode Zen free (Pi), OpenRouter free, NVIDIA NIM (Pi), local models.
- **Paid:** Opus / Sonnet 5.5, GPT-6.1 Sol, DeepSeek, Kimi, GLM — potani key thi.

### 4.15 Poolside Pool
| Level | Models |
|---|---|
| MEDIUM + free | Laguna M.1 (SWE-V 74.6%), Laguna S 2.1 |
| LOW + free | Laguna XS 2.1 (70.9%) |
| Baki | OpenRouter key thi 300+ models |

### 4.16 Qoder CLI (credit multiplier)
| Level | Models |
|---|---|
| HIGH + premium | Performance / Ultimate tier, Qwen3.8 Max, Kimi K3, DeepSeek V4 Pro |
| MEDIUM + premium | Auto (default), Qwen3.7 Max, Kimi K2.7 Code, GLM 5.3 / 5.2, DeepSeek V4 Flash |
| LOW | **Basic / Lite (Free, limited) = LOW + free**; Efficient tier, Qwen3.7 Plus, MiniMax M3 |

### 4.17 Qwen Code (free bandh)
| Level | Models |
|---|---|
| HIGH + premium | Qwen3.8 Max (SWE-Pro 67.7%), Qwen3.7 Max |
| MEDIUM + premium (Coding Plan ¥200) | Qwen3.7 Plus, Qwen3.6 / 3.5 Plus, Qwen3-Coder Plus / Next, GLM-5, Kimi K2.5, MiniMax M2.5 |
| LOW / MEDIUM + free | OpenRouter free, local (Ollama / vLLM) |

### 4.18 Trae CLI (badhu unverified)
| Level | Models |
|---|---|
| HIGH + premium | Claude / GPT / Gemini (version ajanya) |
| MEDIUM | Doubao-Seed-Code, GLM-5 / 5.1, Kimi K2.5, MiniMax M2.5 |
| LOW / MEDIUM + free | Auto (Free plan) |

### 4.19 ZeroClaw
- Potana models nathi — je provider set karo e (Anthropic, OpenAI, Gemini, OpenRouter, Ollama …). **Ollama local = LOW + free.**

---

## 5. Local LLM support karta agents — alag yaadi

> Local LLM = user na potana machine / LAN par chaltu model (Ollama, LM Studio, vLLM, llama.cpp). Aa agents ma e sidhu jodai shake — F5 ni local-LLM script aa agents mate.

### 5.1 Local LLM jodi shake (13)

| # | Agent (OpenClaw id) | Kevi rite joday | Note |
|---|---|---|---|
| 1 | **Kilo Code** (`kilocode`) | Built-in `ollama`, `lmstudio`; `openai-compatible` (baseURL) | `tool_call: true` ane context limit set karva; mukhya |
| 2 | **OpenCode** (`opencode`) | `@ai-sdk/openai-compatible` + baseURL — Ollama `:11434/v1`, LM Studio `:1234/v1`, llama.cpp `:8080/v1` | Ollama ma `num_ctx` 16–32k; mukhya |
| 3 | Codex CLI (`codex`) | `--oss` (Ollama / LM Studio); custom provider | Custom endpoint **Responses API** j joie (Chat Completions nahi) |
| 4 | GitHub Copilot CLI (`copilot`) | `COPILOT_PROVIDER_BASE_URL` — Ollama / OpenAI-compatible | Model ma tool calling + streaming joie; 128k+ context; `COPILOT_OFFLINE=true` |
| 5 | Factory Droid (`droid`) | `customModels` — Ollama `:11434/v1`, LM Studio `:1234/v1`, vLLM | Paid plan joie (Pro $20) |
| 6 | Qwen Code (`qwen`) | `OPENAI_BASE_URL` ke `~/.qwen/settings.json` — Ollama, vLLM | LM Studio (unverified) |
| 7 | Pi (`pi`) | `~/.pi/agent/models.json` — Ollama, LM Studio, vLLM, SGLang, llama.cpp | |
| 8 | fast-agent (`fast-agent`) | `generic` provider (base_url) | Ollama default URL (unverified) |
| 9 | Mux / Xum (`mux`) | Ollama; OpenAI-compatible / Anthropic endpoint | |
| 10 | Poolside Pool (`pool`) | `ollama launch pool --model …` | Poolside na Laguna models local |
| 11 | ZeroClaw (`zeroclaw`) | Ollama; `custom:` OpenAI-compatible | |
| 12 | Grok Build (`grok-build`) | `~/.grok/config.toml` ma custom `base_url` | Beta |
| 13 | MiniMax Code (`mcode`) | `mcode provider add --base-url … --api-format openai-completions` | Local official rite confirm nathi (unverified) |

### 5.2 Fakt khas rite / confirm nathi

| Agent | Sthiti |
|---|---|
| Gemini CLI (`gemini`) | Fakt Google nu **Gemma 4** local (`gemini gemma`); biju local model nahi |
| Trae CLI (`trae`) | Config thi custom model (unverified) |
| Claude Code (`claude`) | Sidhu nahi — fakt Anthropic-compatible gateway thi (unverified) |
| Kimi Code (`kimi`) | Anthropic / OpenAI / Google key; local (unverified) |

### 5.3 Local LLM **nathi** jodatu

| Agent | Karan |
|---|---|
| Cursor CLI (`cursor`) | Custom base URL / Ollama documented nathi |
| Kiro CLI (`kiro`) | Potani key ke custom endpoint j nathi |
| Qoder CLI (`qoder`) | Custom models fakt amuk cloud providers (Alibaba, DeepSeek, Kimi …); local nahi |

### 5.4 Research ma malela local models (free — user na hardware par)

| Model | Kon nu | Level | Kya thi |
|---|---|---|---|
| gpt-oss-120b | OpenAI (open weights) | LOW + free | SWE-V 62.4%; Codex `--oss` |
| gpt-oss-20b | OpenAI (open weights) | LOW + free | SWE-V 60.7%; Codex `--oss` |
| Gemma 4 | Google (open weights) | LOW + free | Gemini CLI `gemini gemma` |
| Laguna XS 2.1 (open weights) | Poolside | LOW + free | SWE-V 70.9%; Ollama |
| Aapni hardware tier list (Qwen2.5-Coder 3B … 32B / Qwen3-Coder 30B) | — | Tier pramane | `implementation.md` — local LLM tier T1 … T6 |

---

## 6. Aapna standard sathe melavyu — shu barabar che, shu nahi

| Aapnu standard (implementation.md) | Research shu kahe | Barabar? |
|---|---|---|
| Free agent = Kilo Code / OpenCode jeva, mahino ke vadhare free | Kilo ane OpenCode ma ghana free models — pan **"limited time"**, ane free list vaaramvaar badlay | ✅, pan list live levi pade (Nexpath ranking list vaaramvaar update) |
| Easy → free agent + free model (ranking list) | Free MEDIUM models (Inkling Small 80.2%, Dots 3 78.4%, MiniMax M3 80.5% Droid Core) saru kaam kare | ✅ |
| Complex → user nu pro plan agent | HIGH models badha paid (Claude, Codex, Cursor, Copilot Pro+, Droid) | ✅ |
| Gemini CLI = free agent (Q-26 / E-1 dakhla ma "Gemini CLI login vagar free") | **Have free nathi** (18 June 2026) | ❌ — E-1 nu dakhlu ane suggestion list badalvi |
| 21 OpenClaw agents | iFlow bandh — kadhyo (20); 5 nava registry ma | ⚠️ — list update joie |
| Local LLM Kilo Code / OpenCode thi (F5 script) | Banne ma Ollama / LM Studio / OpenAI-compatible sidhu che | ✅ |
| Free models no data | Ghana free models prompts **training mate vapre** (Meta Muse, stealth, NVIDIA trial) | ⚠️ — user na code mate privacy; ranking list ma nishani joie |

---

## 7. Haju confirm karvanu (unverified)

- Trae CLI fakt Enterprise mate che ke nahi; ena models.
- Cursor na plan naam (be pages alag kahe); Free plan CLI ma chale ke nahi.
- Codex / Copilot no Free plan CLI ma chale ke nahi.
- Gemini API key no free tier (Flash, 250 / divas) 18 June pachi pan che ke nahi.
- Nava models (Opus 5.5, GPT-6.x, Gemini 4 Argon, Kimi K3) na chokkas coding aankda.
- Step 5 Preview, Big Pickle jeva free models ketla divas free rahese.

---

## 8. Aagal nu pagluu — user reviews (Discord / Reddit)

Tame kahyu tem, list pachi: darek mukhya model / agent mate Discord ane Reddit (r/LocalLLaMA, r/ChatGPTCoding, r/ClaudeAI, Kilo / OpenCode Discord) par real user anubhav — kaam nu ke nahi, tool call bhool, dhimu, limit jaldi puri — ane e parthi aakhri ranking. **Haju sharu nathi karyu.**

---

## 9. Sources

**OpenClaw:** docs.openclaw.ai/tools/acp-agents-setup · github.com/openclaw/acpx/blob/main/docs/agents.md · github.com/openclaw/acpx/releases · github.com/openclaw/openclaw/releases

**Claude / Codex / Copilot / Cursor / Droid:** code.claude.com/docs/en/model-config · claude.com/pricing · learn.chatgpt.com/docs/models · learn.chatgpt.com/docs/pricing · docs.github.com/en/copilot/reference/ai-models/supported-models · docs.github.com/en/copilot/concepts/billing/individual-plans · docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/use-byok-models · github.blog/changelog/2026/04/27/github-copilot-is-moving-to-usage-based-billing/ · cursor.com/docs/models · cursor.com/pricing · cursor.com/docs/settings/api-keys · docs.factory.com/pricing · docs.factory.com/cli/user-guides/choosing-your-model · docs.factory.com/cli/configuration/byok

**Gemini / Grok / Kimi / Kiro / MiniMax:** geminicli.com/docs/resources/quota-and-pricing/ · geminicli.com/docs/cli/model/ · github.com/google-gemini/gemini-cli/discussions/28017 · docs.x.ai/build/overview · amplifying.ai/coding-agents/grok-build · kimi.com/en/help/membership/membership-pricing · kimi.com/en-cn/help/kimi-code/cli-getting-started · kiro.dev/pricing/ · kiro.dev/docs/models/available-models/ · platform.minimax.io/docs/m-plan/intro.md · agent.minimax.io/docs/cli/faq.md

**Kilo / OpenCode / Qwen / Pi / fast-agent / OpenRouter:** api.kilo.ai/api/gateway/models (live) · kilo.ai/docs/code-with-ai/agents/auto-model · kilo.ai/docs/code-with-ai/agents/custom-models · kilo.ai/pricing · opencode.ai/zen/v1/models (live) · opencode.ai/docs/zen/ · opencode.ai/docs/go/ · opencode.ai/docs/providers/ · openrouter.ai/api/v1/models (live) · openrouter.ai/docs/api/reference/limits · github.com/QwenLM/qwen-code · qwenlm.github.io/qwen-code-docs/en/users/configuration/auth/ · help.aliyun.com/en/model-studio/coding-plan · github.com/badlogic/pi-mono · fast-agent.ai/models/llm_providers/

**Mux / Pool / Qoder / Trae / ZeroClaw:** github.com/coder/mux · xum.cdr.dev/config/models · docs.poolside.ai/cli/pool · huggingface.co/poolside/Laguna-XS-2.1 · docs.qoder.com/en/cli/model · docs.qoder.com/account/pricing · trae.ai/pricing · clawhub.ai/alexjunanjing-2/openclaw-traecli · github.com/zeroclaw-labs/zeroclaw

**Benchmarks:** benchlm.ai/benchmarks/swe-bench-verified · benchlm.ai/benchmarks/swe-bench-pro · benchlm.ai/benchmarks/terminal-bench-2 (badha 14 Oct 2026) · vals.ai/benchmarks/swebench · epoch.ai/benchmarks/swe-bench-verified
