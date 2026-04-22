# Media Skills

Claude Code / Codex Skills for content creation — covering topic discovery, brief building, article writing, polishing, review, and publishing.

## Skills

| Skill | Description | Status |
|-------|-------------|--------|
| `content-brief-builder` | Turn a selected topic into a structured content brief (reader, purpose, core argument, SCQA, evidence) | Done |
| `wechat-article-writer` | Write complete WeChat public account articles from a brief | Planned |
| `content-topic-radar` | Multi-source topic discovery and scoring | Planned |
| `content-polisher` | Title/opening/ending optimization, de-AI-ification | Planned |
| `voice-script-writer` | Convert articles into oral scripts for video | Planned |
| `adversarial-content-review` | Multi-role adversarial content review with scoring | Planned |
| `interview-to-draft` | Interview-style idea extraction into briefs or drafts | Planned |
| `wechat-draft-publisher` | Publish Markdown articles to WeChat draft box | Planned |
| `writing-hub` | Orchestrate the full writing pipeline | Planned |

## Architecture

Hub & Spoke — each skill is independent, connected through shared intermediate products (Markdown files).

```
content-topic-radar
    → topic-pool.md
content-brief-builder
    → content-brief.md
wechat-article-writer
    → article-draft.md
content-polisher + adversarial-content-review
    → revised article-draft.md
voice-script-writer
    → voice-script.md
wechat-draft-publisher
    → publish result
```

## Shared References

The `_shared/` directory contains shared rules and templates used by multiple skills:

- `intermediate-format.md` — canonical format spec for all intermediate products

## Installation

```bash
# Clone the repo
git clone https://github.com/Abigale-cyber/media-skills.git

# Symlink a skill to your Claude Code skills directory
ln -s /path/to/media-skills/writing/content-brief-builder ~/.claude/skills/content-brief-builder
```

## License

MIT
