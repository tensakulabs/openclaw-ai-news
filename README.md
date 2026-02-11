# ai-news-skill

AI industry news aggregation skill for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) and [OpenClaw](https://openclaw.ai). Never miss a major model release again.

## Why?

GLM-5 dropped and your morning briefing missed it? Same. This skill monitors 10 curated RSS feeds covering major AI labs and news aggregators so you catch:

- Model releases (GPT, Claude, Gemini, Grok, GLM, Llama, etc.)
- Research papers and benchmarks
- Industry moves (funding, acquisitions, hires)
- Product updates and API changes

## Quick Start

### 1. Install

```bash
# Claude Code
git clone https://github.com/tensakulabs/ai-news-skill.git ~/.claude/skills/ai-news

# OpenClaw
git clone https://github.com/tensakulabs/ai-news-skill.git ~/.openclaw/skills/ai-news
```

### 2. Use

In any Claude Code or OpenClaw session:
```
/ai-news
```

Or just ask: "What's new in AI?" / "Morning AI briefing"

### 3. Automate (Optional — OpenClaw)

Add to your OpenClaw cron jobs for automatic morning briefings:

```bash
openclaw cron add \
  --name "AI Briefing" \
  --cron "0 7 * * *" \
  --isolated \
  --message "Run /ai-news, summarize top 10 items" \
  --announce \
  --channel telegram \
  --to "YOUR_CHAT_ID"
```

For Claude Code, invoke `/ai-news` manually or via system cron.

## Feeds

### News Aggregators

| Source | Frequency | Description |
|--------|-----------|-------------|
| [TLDR AI](https://tldr.tech/ai) | Daily | Curated AI digest |
| [Hacker News](https://news.ycombinator.com) | Real-time | Tech community, viral AI posts |
| [The Decoder](https://the-decoder.com) | Daily | AI-focused news site |
| [Last Week in AI](https://lastweekin.ai) | Weekly | Comprehensive roundup |
| [Marktechpost](https://marktechpost.com) | Daily | Research and papers |

### Lab Blogs

| Lab | Feed | Covers |
|-----|------|--------|
| Anthropic | [News](https://raw.githubusercontent.com/Olshansk/rss-feeds/main/feeds/feed_anthropic_news.xml) | Claude releases |
| OpenAI | [Research](https://raw.githubusercontent.com/Olshansk/rss-feeds/main/feeds/feed_openai_research.xml) | GPT releases |
| xAI | [News](https://raw.githubusercontent.com/Olshansk/rss-feeds/main/feeds/feed_xainews.xml) | Grok releases |
| Google | [AI Blog](https://raw.githubusercontent.com/Olshansk/rss-feeds/main/feeds/feed_google_ai.xml) | Gemini, DeepMind |
| Anthropic | [Changelog](https://raw.githubusercontent.com/Olshansk/rss-feeds/main/feeds/feed_anthropic_changelog_claude_code.xml) | Claude Code updates |

Lab blog feeds via [Olshansk/rss-feeds](https://github.com/Olshansk/rss-feeds).

## Known Gaps

These major labs don't publish RSS feeds:

- **Zhipu AI** (GLM series) - China
- **DeepSeek** - China
- **Baidu** (ERNIE) - China
- **Alibaba** (Qwen) - China
- **Meta AI** - USA
- **Mistral AI** - France

The skill reminds you to check these manually.

## Customization

Edit `feeds.json` to add/remove feeds or change priorities.

Optional feeds you can enable:
- Anthropic Engineering (technical posts)
- Anthropic Research (papers, alignment)
- The Batch (Andrew Ng's newsletter)
- TechCrunch AI
- VentureBeat AI

## Contributing

PRs welcome! Especially:
- New RSS feed sources
- Better categorization logic
- Feeds for labs in the "Known Gaps" section

## License

MIT

---

Made by [Tensaku Labs](https://tensakulabs.com)
