<div align="center">

# 🔥 sell-or-die

**The market is brutal. A sharp-tongued, branch-by-branch discovery Agent Skill that grills physical e-commerce sellers into verifiable selling-point truth bases.**

*市场是残酷的 —— 面向实物电商的「毒舌拷问式」卖点挖掘与资产底座 Agent Skill*

<a href="README.md"><img alt="简体中文 · Switch" src="https://img.shields.io/badge/%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-Switch-555?style=for-the-badge"></a>
<a href="README.en.md"><img alt="English · Current" src="https://img.shields.io/badge/English-Current-111?style=for-the-badge"></a>

[![Agent Skill](https://img.shields.io/badge/Agent-Skill-blue.svg)](#)
[![Compatible](https://img.shields.io/badge/Compatible-Claude%20Code%20%7C%20Codex%20%7C%20Cursor-black.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#license)

</div>

---

## Why `sell-or-die`?

Asking a general LLM to "extract product selling points" for physical e-commerce usually fails in four predictable ways:

1. **Echo-Chamber Fluff**: Vague input ("soft fabric, flattering fit") turns into a wall of clichés that loses livestream viewers within 3 seconds.
2. **Zero Refund Defense**: Ignoring physical trade-offs and mismatched buyer profiles drives high return rates that wipe out ad margins.
3. **Compliance Landmines**: Brand-knockoff wording, medical claims, or illegal superlatives slip straight into downstream scripts and trigger platform penalties.
4. **Negative-Prompt Leakage (Pink Elephant Trap)**: Writing what a product *lacks* (e.g., "no chest logo, no side slits") often gets copied by downstream image/video agents into prompts—causing generative models to render the exact forbidden details.

`sell-or-die` never drifts into writing ad scripts. It acts as a **no-nonsense e-commerce operator** who interrogates you in 4–6 fast turns and outputs a clean, verified **Markdown Selling-Point Truth Base** ready for downstream livestream scripts, short-video workflows, or AI visual pipelines.

---

### Key Features

* **Fail-Fast Compliance Pre-Check**: Immediately flags trademark knockoffs, therapeutic/medical claims, superlatives, and unexplained price gaps (pre-configured for **Douyin & China Advertising Law**, easily customizable in `SKILL.md` for TikTok Shop / Amazon / FTC rules).
* **Hero SKU Locking**: Locks the exact target variant, color, and price upfront so specs and offers never contradict each other across SKUs.
* **Targeted Sharpness & Fast Convergence**: Pushback is strictly reserved for fluff, hype, or blind spots (capped at 1 sentence); solid facts are confirmed immediately with zero sarcasm. Max 2 turns per branch with an explicit `[TBD]` honesty valve so users are never cornered into fabricating specs.
* **Dynamic Competitive Positioning × 3–10s On-Camera Proof**: Automatically chooses the real conversion battle (vs. cheap low-quality alternatives / vs. overpriced big brands / vs. customer inertia) and pairs every claim with a concrete 3–10 second physical camera demo.
* **Positive-Only Visual Anchors**: Records only physically present visual geometry and surface traits—zero negative feature descriptions—eliminating downstream generative artifacts.
* **Pure Asset Base Output**: Runs a silent cross-turn consistency check before generating a fixed 6-section Markdown spec sheet with sanitized compliance replacement mappings.

---

### Workflow

```text
[One-line cold start OR messy supplier specs / raw notes]
                           │
                           ▼
   Step 0: Fact Extraction + Hero SKU Lock + Fail-Fast Compliance Check
                           │
                           ▼
   ┌─────────────────────────────────────────────────────────────────┐
   │  4-Branch High-Density Interrogation (1-2 Qs/turn, 2-turn cap)  │
   │  [1/4] Hero SKU Specs & Positive-Only Visual Anchors            │
   │  [2/4] Dynamic Competitor Contrast × 3-10s On-Camera Proof      │
   │  [3/4] Real Flaws, Disqualified Buyers & Refund Traps           │
   │  [4/4] Price Logic (Why So Cheap), Delivery Package & Redlines  │
   └─────────────────────────────────────────────────────────────────┘
                           │
                           ▼
   Step 2: Silent Consistency Check ──▶ Clean Markdown Selling-Point Asset Base
                                        (Ready for downstream script & AI visual pipelines)
```

---

### Installation & Usage

#### Repository Layout

```text
sell-or-die/
├── SKILL.md
├── README.md
├── README.en.md
└── LICENSE
```

Clone into your Agent Skills directory (Claude Code, Codex, OpenCode, Cursor, etc.):

```bash
git clone https://github.com/w2968066/sell-or-die.git ~/.agents/skills/sell-or-die
```

* **Claude Code / Codex / OpenCode**: drop it into `.claude/skills/`, `.codex/skills/`, or `.agents/skills/`.
* **Cursor / other `SKILL.md`-compatible agents**: import the root `SKILL.md`.

Trigger with either a one-liner or a raw spec dump:

```text
# Cold start
Use sell-or-die: I'm selling a dual-layer memory foam pillow at $9.90 vs. $55 hotel-grade retail pillows.

# Raw spec dump (known facts locked automatically; only gaps are grilled)
Run sell-or-die on my supplier notes: [paste specs/notes]
```

Type `stop` or `output document now` at any point to compile early; unresolved fields are safely marked `[TBD]`.

---

### Output Document Schema

Every completed session produces a pure, script-free Markdown brief with 6 sections:

1. **Hero SKU & Physical Hard Specs** (variant notes + `[TBD]` unverified list)
2. **Positive-Only Visual Anchors** (camera & AI visual consistency baseline)
3. **Competitor Contrast × 3–10s On-Camera Proof Library** (battlefield + prop/action/result)
4. **Real Flaws, Disqualified Buyers & Refund Defense** (trade-offs + day-1 unboxing expectations + sizing logic)
5. **Price Logic, Delivery Package & Compliance Redlines** (Why So Cheap + box contents + sanitized replacement mapping)
6. **Downstream Pipeline Handoff Summary** (compliant one-liner + top 3 verifiable hooks + #1 return risk)

---

### Inspiration & Credits

This workflow synthesizes patterns from:

* [`grill-me`](https://github.com/mattpocock/skills) — Branch-by-branch relentless questioning & never re-asking known facts
* [`interview-me`](https://github.com/addyosmani/agent-skills) — Low-friction conversational pacing (1–2 questions per turn)
* [`discovery-interview-prep`](https://github.com/deanpeters/Product-Manager-Skills) — JTBD & real-alternative failure-mode probing
* [`prd`](https://github.com/github/awesome-copilot) — Strict output gate, anti-fluff enforcement & structured spec synthesis

---

## License

[MIT](LICENSE). Free to use, fork, and adapt to your own e-commerce categories and platform compliance rules.

<div align="center">

<a href="README.md"><img alt="阅读中文版" src="https://img.shields.io/badge/%E9%98%85%E8%AF%BB%E4%B8%AD%E6%96%87%E7%89%88-%E2%86%92-555?style=for-the-badge"></a>

</div>
