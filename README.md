# 𝚊𝚛𝚝𝚒𝚜𝚝 𝚜𝚔𝚒𝚕𝚕𝚜

A library of agent skills for digital artists.

## Available Skills

- **manifold-integration** - Add Manifold NFT auction and sale widgets to your website.
- **create-curated-gallery** - Create or update a one-page curated gallery from Manifold listings with referral-enabled listing links.

## Installation

Choose one of the methods below to install skills into your AI agent.

### Manual Installation

#### Step 1: Download from GitHub

1. Go to the [repository page](https://github.com/0xGh/artist-skills)
2. Click the green **Code** button
3. Select **Download ZIP**
4. Extract the ZIP file to a temporary location

#### Step 2: Copy the skill folder

Navigate into the extracted folder and find the skill you want inside the `skills/` directory. Copy it to your agent's skills directory.

**For Claude Code:** Copy the skill folder to `~/.claude/skills/`

- On **macOS/Linux**: `~/.claude/skills/`
- On **Windows**: `C:\Users\YOUR_USERNAME\.claude\skills\`

Example: To install `create-curated-gallery`, copy the entire `skills/create-curated-gallery` folder so you end up with `~/.claude/skills/create-curated-gallery/`

**For other agents:** Replace `~/.claude/skills/` with your agent's skills directory.

#### Note: Showing hidden folders

The `.claude` folder is hidden because its name starts with a dot. To see it:

- **macOS Finder**: Press `Cmd + Shift + .` (period) to toggle hidden files
- **Windows Explorer**: Click **View** in the menu bar, then check **Hidden items**
- **Linux file managers**: Press `Ctrl + H` to toggle hidden files

If the `.claude` folder doesn't exist yet, create it first, then create a `skills` folder inside it.

### Easy Install: Using the add-skill tool (requires Node.js/npm)

If you have Node.js or npm installed, you can use the `add-skill` package:

**Install a specific skill:**
```bash
npx add-skill https://github.com/0xGh/artist-skills --skill manifold-integration

# or
npx add-skill https://github.com/0xGh/artist-skills --skill create-curated-gallery
```

**List all available skills first:**
```bash
npx add-skill https://github.com/0xGh/artist-skills --list
```

**Install globally (for all projects):**
```bash
npx add-skill https://github.com/0xGh/artist-skills --skill manifold-integration --global

# or
npx add-skill https://github.com/0xGh/artist-skills --skill create-curated-gallery --global
```

## License

AGPL-3.0-or-later

Copyright (c) 2026-or-later 0xG
