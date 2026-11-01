<div align="center">

# 🍀 Clover RPG · Character Builder

**Plan your stats, race, family, weapon, traits and spells before you spend a single point.**

[![Live](https://img.shields.io/badge/live-clover--rpg--builder.netlify.app-1f6b4a?style=for-the-badge&logo=netlify&logoColor=white)](https://clover-rpg-builder.netlify.app)
![Vanilla JS](https://img.shields.io/badge/vanilla-JavaScript-8a6410?style=for-the-badge&logo=javascript&logoColor=white)
![Zero dependencies](https://img.shields.io/badge/dependencies-0-62c592?style=for-the-badge)
![Single file](https://img.shields.io/badge/single-HTML%20file-1b2a22?style=for-the-badge&logo=html5&logoColor=white)

[**Open the builder →**](https://clover-rpg-builder.netlify.app)

</div>

---

> **Unofficial fan project.** Not affiliated with the developers of Clover RPG. The game is in early access and numbers change often, so always double-check in game before spending points.

## 🌿 What is this?

A fast, mobile-friendly build planner for **Clover RPG** on Roblox, inspired by the Deepwoken builder. Pick your stats and see exactly which traits you can afford, what each buff adds up to, and how much damage your weapon will deal.

> The interface is in **Brazilian Portuguese (pt-BR)**.

## ✨ Features

| | Feature | Details |
|---|---|---|
| 📊 | **Stats & level** | Six stats (Strength, Agility, Vitality, Intelligence, Endurance, Magic Power) with live point budgets. Max level 80. |
| 🧬 | **Race & family** | 7 races and a full family list grouped by rarity (Legendary → Common), with their passive bonuses. |
| ⚔️ | **Weapon calculator** | 60+ weapons across Light / Medium / Heavy. Compares base damage, damage with proficiency, final damage with buffs, and damage × speed. |
| 🎯 | **Calibration** | Enter your own `k` from the in-game tooltip to turn the estimate into accurate numbers. |
| 🧠 | **Traits** | Searchable, filterable by category. Shows requirements (stats, level, marks, quests, kills) and prerequisite chains with total cost. |
| 🔮 | **Spells (Grimoire)** | Passives for Flame, Wind, Lightning, Shadow, Time and more, with Marks and Insight costs. |
| ➕ | **Buff totals** | Every buff is summed and grouped (Offensive, Defense, Energy, Progression), with the source of each shown. |
| ⚡ | **Conditional buffs** | Toggle situational effects (low health, after a guard break…) to simulate them in your totals. |
| 🔗 | **Share builds** | Compact code or link, plus a "copy build" text summary. Import by pasting either one. |
| 🌗 | **Light & dark** | Follows your system theme. Built mobile-first, with safe-area support. |

## 📐 Rules the builder uses

- Max level is **80**.
- The level 1 character starts with no points.
- **Each level from 2 onward** grants **2 stat points** and **1 skill point**.
- Traits and spell passives spend **skill points**; stats spend **stat points**.
- Weapon proficiency costs **2 stat points and 15 Insight per level**; going above level 3 requires Percival's recommendation.
- Elemental family bonuses only count if you picked the matching spell.

### Weapon damage formula

```text
damage = base × (1 + scaling × proficiency × k / 100)
```

The game does not publish `k`. To find yours, read the weapon damage from its tooltip and solve:

```text
k = (tooltip ÷ base − 1) × 100 ÷ (scaling × proficiency)
```

Leaving `k` empty uses an **unofficial estimate of 1**.

## 🚀 Run it locally

There is nothing to build or install. It is a single `index.html`.

```bash
git clone https://github.com/<your-user>/<your-repo>.git
cd <your-repo>
# just open it
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

Or serve it with any static server:

```bash
npx serve .
# or
python3 -m http.server 8000
```

## 🔗 Sharing format

Builds are encoded as a compact **Base58** string (about 40 characters or less) containing level, stats, race, family, enchant, weapon class, proficiency, traits and spell passives.

- **Code:** paste it into the import field.
- **Link:** `https://clover-rpg-builder.netlify.app/#b-<code>` loads the build directly.
- The selected weapon, calibration `k` and conditional toggles are stored **only in your browser** (`localStorage`), not in the code.

## 🗂️ Project structure

```text
.
├── index.html   # HTML, CSS and JS, all in one file
└── README.md
```

All game data (traits, races, families, enchants, weapons, spell passives) lives in plain arrays at the top of the script, so updating it after a patch is just editing a line.

## 🤝 Contributing

Game data comes from the Clover RPG wiki and community sources, and it can be outdated or incomplete. Corrections are very welcome:

1. Fork the repo
2. Edit the relevant data array in `index.html`
3. Open a pull request with a link or screenshot that confirms the change

Good first contributions: missing Light magic passives, family bonuses for the Common tier, and confirmed contract effects for Lesser Demon and Lesser Angel.

## 🙏 Credits

- Game data: Clover RPG wiki and the community
- Inspiration: the Deepwoken builder
- Fonts: [Fraunces](https://fonts.google.com/specimen/Fraunces) and [Figtree](https://fonts.google.com/specimen/Figtree) via Google Fonts

<div align="center">

Made with 🍀 for the Clover RPG community

</div>
