# important-prompts

I use this repository to store the **most important system prompts** I rely on across projects — the ones worth versioning, reusing, and keeping stable over time.

This is not a dump of every prompt I ever wrote. Only prompts that materially shape how an agent or workflow behaves belong here.

## What's inside

| Path | Description |
|------|-------------|
| [`prompts/hiring_expert_system_prompt.md`](prompts/hiring_expert_system_prompt.md) | IT hiring advisor — CV analysis, Germany market comparison, `/analyse`, `/improve`, `/interview` shortcuts, human voice + XYZ bullet rules |

## How I use it

1. Copy the **SYSTEM PROMPT** block from a file into Cursor rules, Custom GPT instructions, or an API `system` message.
2. Keep project-specific assets (CV, reports, scripts) **local** — they are not part of this repo.
3. When a prompt changes meaningfully, commit and push so all my environments stay in sync.

## Hiring expert shortcuts (reference)

| Shortcut | Purpose |
|----------|---------|
| `/analyse` | Full profile analysis report (Germany market) |
| `/improve` | Before/after CV improvements table |
| `/interview` | Strict recruiter mock interview from latest improvements |

Full behaviour is defined in `prompts/hiring_expert_system_prompt.md`.

## License

Personal use. Adapt freely for your own career tooling.
