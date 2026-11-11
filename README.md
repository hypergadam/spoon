<h1 align="center"><img src="spoon-title.svg" alt="🥄 spoon" height="120"></h1>

<h3 align="center">Absurdly simple, seriously powerful.</h3>

<p align="center">
  <a href="https://youtu.be/Q5Ichk3hjfs">
    <img src="spoon-youtube-banner.png" alt="Watch the spoon explainer video on YouTube" width="720">
  </a>
  <br>
  <sub>▶️ <a href="https://youtu.be/Q5Ichk3hjfs">Watch the explainer video</a></sub>
</p>

---

## 🤔 I'm busy. What is it?

spoon is a tiny skill that works on every major agent platform (Claude Code, Codex, Cursor and more). It takes seconds to start with and is absurdly simple. Here's the problem it solves: LLMs can't guess how long you want an answer to be, or how much effort to put into checking that it's correct. And by 3 pm, after reading hundreds of paragraphs, you're too tired for another wall of text.

With spoon, you add a tiny token like `1m` (a 1-minute read) or `ver` (verify before answering) instead of writing out a sentence of instructions, and you get exactly the answer you wanted: the right length, the right shape, and checked. The [1.5-minute explainer video](https://youtu.be/Q5Ichk3hjfs) shows it in action.

---

## ⚡ Start in 30 seconds

**1. Install** with [skills.sh](https://skills.sh) (works with Claude Code, Codex, Cursor and more):

```bash
npx skills add practicajs/spoon --skill spoon
```

…or use your favorite marketplace ([Claude Code, Codex](#-install)).

**2. Open your favorite AI editor** and type `sp`, then a token or two, then your question:

```
sp 1m   why is my app slow?                                 → a 1-minute read
sp 3s   what are MCPs?                                      → 3 sentences
sp ver  can iOS send notifications while the phone sleeps?  → checked before it's sent
sp 1m cr da   should we move to the cloud?                  → 1 minute, crystal clear, with data
```

Tokens can also go at the end of the message. Every answer ends with 🥄 and a short note on what your tokens did.

---

## 📋 Cheat sheet

### 🍽️ Dosing — how much

| Token | You get |
|---|---|
| `{n}s` | `n` sentences (not seconds) |
| `{n}p` | `n` short paragraphs |
| `{n}m` | about `n` minutes to read (1m ≈ 200 words) |

> The dose always wins. Everything else must fit inside it.

### ✅ Verification — how sure

| Token | Level | What happens |
|---|---|---|
| `ver1` / `thoughtful` | 🧠 Thoughtful | care and sources, no subagents |
| `ver2` / `sampling` | 🔍 Sampling | subagents check key claims |
| `ver3` / `consensus` | 🤼 Consensus | two models must agree |
| `ver` | 🎯 Auto | easy → thoughtful, right/wrong → consensus, long research → sampling |

### ✨ Enhancers — how it's made

| Token | You get |
|---|---|
| `cr` / `crystal` | crystal clear, via subagents |
| `lay` | explained to a layman |
| `qu` | a question for you first |
| `in` / `out` | more / less detail |
| `da` / `data` | backed by verified data |

### 🎨 Formats — what shape

| Token | You get |
|---|---|
| `bul` | a few bullets with bold titles |
| `art` | an artifact |
| `html` | an HTML artifact |

### 🧰 Utilities

| Token | You get |
|---|---|
| `tips` | a two-line quick start |
| `sticky on` | keep the tokens for the session |
| `sticky off` | stop keeping them |

---

## 🚀 Powerful & advanced

<details>
<summary><b>Combine anything</b></summary>

```
sp 2p ver3 bul       → 2 paragraphs, as bullets, verified by consensus
sp 1m lay cr         → 1 minute, for a layman, crystal clear
sp 5s out html       → 5 sentences, big picture, as an HTML artifact
```
</details>

<details>
<summary><b>Set it once with <code>sticky</code></b></summary>

```
sp 1m bul sticky on   → every answer: 1 minute, bullets
sp sticky off         → back to normal
```
</details>

<details>
<summary><b>Crystal: a mini editing team</b></summary>

Claude writes a draft. Three helpers each suggest one edit:

- **Simplicity** — make it simpler
- **Completeness** — add a missing detail
- **Show, don't tell** — add an example

A judge accepts or rejects each edit. Only agreed edits go in.
</details>

---

## 🔬 How verification works

| Level | Cost | Best for |
|---|---|---|
| 🧠 Thoughtful | 💲 | easy, closed questions |
| 🔍 Sampling | 💲💲 | long, multi-part answers (a few sentences or less → consensus) |
| 🤼 Consensus | 💲💲💲 | right/wrong questions with few parts |

<details>
<summary><b>🔍 Sampling</b> — check the claims that matter</summary>

```
draft → pick up to 3 key claims → 1 subagent per claim → all correct? send : revise
```
</details>

<details>
<summary><b>🤼 Consensus</b> — two models argue until they agree</summary>

```mermaid
flowchart LR
  Q[Question] --> A[Opus answers] & B[Sonnet answers]
  A & B --> D{Agree?<br>max 2 rounds}
  D -->|yes| OK[✅ Send]
  D -->|no| J[2 judges vote]
  J -->|3 of 4| OK
  J -->|2–2| W[⚠️ Send with warning]
```

Claude is only the referee. It never votes.
</details>

---

## 📦 Install

**Claude Code** — plugin marketplace:

```
/plugin marketplace add practicajs/spoon
/plugin install spoon@practicajs
```

**Codex** — plugin marketplace:

```bash
codex plugin marketplace add practicajs/spoon
codex plugin add spoon@practicajs
```

**Any agent** — [skills.sh](https://skills.sh) (Claude Code, Codex, Cursor and more):

```bash
npx skills add practicajs/spoon --skill spoon
```

Then type `sp tips`.

<details>
<summary><b>🧪 Evals</b></summary>

```bash
cd evals && npm install && npm run eval
```

More in [`evals/README.md`](evals/README.md).
</details>

<p align="center">🥄</p>
