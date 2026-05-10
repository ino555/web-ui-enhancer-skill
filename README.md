# web-ui-enhancer — Claude Skill

A skill for [Claude](https://claude.ai) that modernizes static websites (HTML/CSS/JS) with contemporary design, animations, and application-appropriate color palettes — without the generic AI dark-blue/purple cliché.

## What it does

Give Claude your plain HTML file and say *"make this look better"* — the skill will:

- **Analyze** the page purpose (cafe, portfolio, SaaS, blog...) and target audience
- **Choose a unique color palette** matched to the app — warm espresso tones for a cafe, editorial cream+coral for a portfolio, clean paper-white for SaaS
- **Add scroll animations** via Intersection Observer (fade-up reveals, staggered delays)
- **Upgrade typography** with Google Fonts pairings (Playfair Display, Space Grotesk, Manrope...)
- **Set up a CSS custom property system** for easy future changes
- **Add hover micro-interactions** on cards, buttons, nav links

### What it avoids

- ❌ Dark `#0d0d0d` + blue/purple neon — the most common AI design cliché
- ❌ Glassmorphism blobs on dark backgrounds
- ❌ All sites looking identical to each other
- ❌ Generic `#667eea → #764ba2` gradients

## Example outputs

| Use case | Result |
|---|---|
| Plain cafe menu | Playfair Display, warm parchment bg, amber gold accents, scroll reveals |
| Bootstrap blue dev portfolio | Space Grotesk, cream + coral, bento grid, no dark theme |
| Purple gradient SaaS page | Manrope, warm paper white, amber CTA, bento feature grid |

See the [`examples/`](./examples/) folder for live HTML output files you can open in a browser.

## Installation

### Prerequisites
- [Claude desktop app](https://claude.ai/download) with the **Skills Plugin** enabled

### One-line install

**Windows (PowerShell):**
```powershell
$target = "$env:USERPROFILE\.claude\plugins\web-ui-enhancer"
New-Item -ItemType Directory -Force -Path "$target\.claude-plugin" | Out-Null
New-Item -ItemType Directory -Force -Path "$target\skills\web-ui-enhancer" | Out-Null
'{"name":"web-ui-enhancer","version":"1.0.0","description":"Modernizes static HTML/CSS/JS sites with contemporary design","author":{"name":"ino555","url":"https://github.com/ino555/web-ui-enhancer-skill"}}' | Out-File "$target\.claude-plugin\plugin.json" -Encoding utf8
Invoke-WebRequest "https://raw.githubusercontent.com/ino555/web-ui-enhancer-skill/main/SKILL.md" -OutFile "$target\skills\web-ui-enhancer\SKILL.md"
Write-Host "Installed! Restart Claude to activate."
```

**macOS / Linux (bash):**
```bash
TARGET="$HOME/.claude/plugins/web-ui-enhancer"
mkdir -p "$TARGET/.claude-plugin" "$TARGET/skills/web-ui-enhancer"
echo '{"name":"web-ui-enhancer","version":"1.0.0","description":"Modernizes static HTML/CSS/JS sites","author":{"name":"ino555","url":"https://github.com/ino555/web-ui-enhancer-skill"}}' > "$TARGET/.claude-plugin/plugin.json"
curl -o "$TARGET/skills/web-ui-enhancer/SKILL.md" \
  "https://raw.githubusercontent.com/ino555/web-ui-enhancer-skill/main/SKILL.md"
echo "Installed! Restart Claude to activate."
```

### Manual install
1. Create this folder structure:
   ```
   ~/.claude/plugins/web-ui-enhancer/
   ├── .claude-plugin/
   │   └── plugin.json
   └── skills/
       └── web-ui-enhancer/
           └── SKILL.md
   ```
2. Copy `SKILL.md` from this repo into `skills/web-ui-enhancer/`
3. Create `plugin.json` with: `{"name":"web-ui-enhancer","version":"1.0.0"}`
4. Restart Claude

## Usage

Once installed, share an HTML/CSS file with Claude and use natural language:

```
"Bu sayfamı daha modern yap"
"Add animations and improve the design"
"Make this look more professional"
"UI'ı güzelleştir, animasyon ekle"
"Redesign this landing page"
```

The skill triggers automatically on phrases like:
`daha güzel yap` · `animasyon ekle` · `modern görünüm` · `tasarımı geliştir` · `frontend iyileştir` · `make it look better` · `add animations` · `improve the design`

## How it works

The skill follows a structured process:

1. **Analysis** — reads the existing HTML and identifies the page type, audience, and current design
2. **Personality definition** — assigns a design character ("Italian espresso bar", "Vogue editor", "Linear/Vercel")
3. **Color selection** — picks a palette derived from the app's feeling, not a generic table
4. **Implementation** — adds Intersection Observer animations, Google Fonts, CSS variables, hover effects
5. **Quality check** — verifies the result doesn't look like another AI-generated site

## License

MIT — free to use, modify, and share.

---

*Built with the Claude Skill Creator.*
