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
$base = "$env:APPDATA\Claude\local-agent-mode-sessions\skills-plugin"
$skillsDir = Get-ChildItem $base -Recurse -Filter "skill-creator" -Directory -ErrorAction SilentlyContinue | Select-Object -First 1 -ExpandProperty Parent
$target = Join-Path $skillsDir.FullName "web-ui-enhancer"
New-Item -ItemType Directory -Force -Path $target | Out-Null
Invoke-WebRequest "https://raw.githubusercontent.com/ino555/web-ui-enhancer-skill/main/SKILL.md" -OutFile "$target\SKILL.md"
Write-Host "Installed to: $target"
```

**macOS / Linux (bash):**
```bash
BASE="$HOME/Library/Application Support/Claude/local-agent-mode-sessions/skills-plugin"
SKILLS=$(find "$BASE" -name "skill-creator" -type d 2>/dev/null | head -1 | xargs dirname)
mkdir -p "$SKILLS/web-ui-enhancer"
curl -o "$SKILLS/web-ui-enhancer/SKILL.md" \
  "https://raw.githubusercontent.com/ino555/web-ui-enhancer-skill/main/SKILL.md"
echo "Installed to: $SKILLS/web-ui-enhancer"
```

### Manual install
1. Copy `SKILL.md` into your Claude skills directory:
   - **Windows:** `%APPDATA%\Claude\local-agent-mode-sessions\skills-plugin\...\skills\web-ui-enhancer\SKILL.md`
   - **macOS:** `~/Library/Application Support/Claude/local-agent-mode-sessions/.../skills/web-ui-enhancer/SKILL.md`
   
   > Tip: Find the right path by searching for the `skill-creator` folder — `web-ui-enhancer` goes in the same `skills/` parent directory.

2. Restart Claude

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
