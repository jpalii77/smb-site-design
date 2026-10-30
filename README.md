# smb-site-design

An agent skill for designing **small-business websites that don't look AI-generated**.
Works with Claude Code, Codex and any coding agent that reads skills.

Ask an agent for "a website for a dental clinic" and you usually get the same thing: cream background, gold accent, purple gradient, three equal cards, and a line about a "unique experience". This skill pulls the agent out of that pattern:

- **Ban list:** 20 familiar tells of AI-made sites, each with what to do instead
- **Sector directions:** clinic, boutique hotel, wedding venue, manufacturer/B2B and beauty salon, with font pairs, palette, layout and trust signals
- **8 page skeletons:** so every site doesn't come out with the same layout
- **No stock photos:** design with type and real information instead
- **10-point pre-delivery check:** mobile, contrast, local characters, fake claims, reduced motion

## Install

Copy the folder into your agent's skills directory:

```bash
git clone https://github.com/jpalii77/smb-site-design.git
cp -r smb-site-design/skills/smb-site-design ~/.claude/skills/
```

Then ask your agent something like: *"Use the smb-site-design skill to build a one-page site for a dental clinic in Lisbon."*

## Why

We build websites for small businesses in Turkey. After many demo sites, the same AI fingerprints kept showing up. These are the rules we now follow on every site.

## License

MIT. Thanks to [impeccable](https://github.com/pbakaus/impeccable), [taste-skill](https://github.com/Leonxlnx/taste-skill), [hallmark](https://github.com/Nutlope/hallmark) and [Open Props](https://github.com/argyleink/open-props).
