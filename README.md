# 𝚊𝚛𝚝𝚒𝚜𝚝 𝚜𝚔𝚒𝚕𝚕𝚜

A library of agent skills for digital artists.

## Available Skills

- **manifold-integration** - Add Manifold NFT auction and sale widgets to your website.
- **create-curated-gallery** - Create or update a one-page curated gallery from Manifold listings with referral-enabled listing links and earn 6.9% of the final sale price on referrals.

## Installation

Choose one method:

- [Terminal](#terminal)
- [Manual](#manual)
- [Claude Desktop](#claude-desktop)

### Terminal (all agents)

Install one skill:

```bash
npx skills add https://github.com/0xGh/artist-skills --skill <skill-name>
```

Example:

```bash
npx skills add https://github.com/0xGh/artist-skills --skill create-curated-gallery
```

### Manual (all agents)

1. Open [https://github.com/0xGh/artist-skills](https://github.com/0xGh/artist-skills)
2. Click **Code** then **Download ZIP**
3. Unzip the folder
4. Open `skills/` and copy the skill folder you want

Copy to your current project's agent skills directory:

- Claude Code: `.claude/skills/`
- Other agents: `.agents/skills/`

If `.claude` or `.agents` is hidden use:

- macOS Finder: `Cmd + Shift + .`
- Windows Explorer: enable **Hidden items**
- Linux file managers: `Ctrl + H`

If `.claude/skills/` or `.agents/skills/` does not exist create it first.

### Claude Desktop

For regular Claude users see the official guide: https://support.claude.com/en/articles/12512180-use-skills-in-claude

## License

MIT

Copyright (c) 2026-or-later 0xG
