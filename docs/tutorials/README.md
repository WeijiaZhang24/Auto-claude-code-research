# ARIS Tutorials

Long-form interview-prep cheat sheets, written in Markdown and rendered to single-file HTML via the `/render-html` skill (academic-newspaper template, sticky TOC, MathJax + highlight.js, cross-model codex review gate).

| Tutorial | MD source | Rendered HTML | Topics |
|---|---|---|---|
| **Attention 面试 Cheat Sheet** | [`attention_tutorial.md`](attention_tutorial.md) | [`attention_tutorial.html`](https://wanshuiyin.github.io/Auto-claude-code-research-in-sleep/tutorials/attention_tutorial.html) | Scaled-dot-product, MHA / MQA / GQA, RoPE / ALiBi, FlashAttention, KV cache, attention in diffusion, NaN-mask trap, 25 高频面试题 |
| **Flow Matching Quick Reference** | [`flow_matching_tutorial.md`](flow_matching_tutorial.md) | [`flow_matching_tutorial.html`](https://wanshuiyin.github.io/Auto-claude-code-research-in-sleep/tutorials/flow_matching_tutorial.html) | Conditional FM, Rectified Flow / VP / VE paths, training + sampling code, ODE solvers, SD3 / FLUX latent FM, 与 diffusion / score-matching 的桥 |

## How they were produced

Each `.md` was rendered via:

```bash
python3 skills/render-html/scripts/render_html.py <tutorial>.md \
  --template academic \
  --author "Ruofeng Yang (杨若峰), Shanghai Jiao Tong University" \
  --eyebrow "Interview Prep · …" \
  --subtitle "…" \
  --title "…"
```

After rendering, a fresh-thread `codex gpt-5.5 xhigh` review checked 13 properties — information fidelity, math/code/table integrity, callout class mapping, `<details>` inner Markdown rendering, sanitization, no path/personal-info leakage, TOC link resolution, heading glue. The per-file audit trail is in `*.review.json`.

> See [`skills/render-html/SKILL.md`](../../skills/render-html/SKILL.md) for the full skill protocol.
