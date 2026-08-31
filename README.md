<div id="user-content-toc">
  <ul align="center" style="list-style: none;">
    <summary>
      <h1>NERV-UI</h1><br>
      <h2>Typed React command-center components, plus a portable agent skill.</h2>
      <p>Build original, sharp industrial dashboards, terminals, and flows in React without rebuilding the design system from scratch.</p>
    </summary>
  </ul>
</div>

<p align="center">
  <img src="banner.png" alt="NERV-UI — Neon Genesis Evangelion Design System" width="100%" />
</p>

<p align="center">
  <img src="docs/references/readme-surveillance-preview.gif" alt="NERV-UI live surveillance preview" width="100%" />
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/@mdrbx/nerv-ui"><img src="https://img.shields.io/npm/v/@mdrbx/nerv-ui?style=flat-square&color=FF9900&labelColor=000000" alt="npm version" /></a>
  <img src="https://img.shields.io/badge/components-48-00FF00?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/examples-18_pages-00FFFF?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/border--radius-0px-FF0000?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/license-MIT-FF9900?style=flat-square&labelColor=000000" />
</p>

<p align="center">
  <a href="https://mdrbx.github.io/nerv-ui/"><img src="https://img.shields.io/badge/LIVE_DEMO-00FFFF?style=for-the-badge&labelColor=000000" alt="Live Demo" /></a>
  &nbsp;
  <a href="https://skills.sh/mdrbx/nerv-ui/nerv-ui"><img src="https://img.shields.io/badge/INSTALL_AGENT_SKILL-00FF00?style=for-the-badge&labelColor=000000" alt="Install Agent Skill" /></a>
  &nbsp;
  <a href="https://mdrbx.github.io/nerv-ui/docs"><img src="https://img.shields.io/badge/DOCUMENTATION-FF9900?style=for-the-badge&labelColor=000000" alt="Documentation" /></a>
</p>

---

## `> START_IN_30_SECONDS`

**NERV-UI is a production React/TypeScript component library, a published npm package, 48 documented components, 18 live application examples, and a portable coding-agent skill.**

- **Want an agent to build with it?** Install the skill with one command below.
- **Want the React components?** Jump to [the npm install](#-install_in_a_react_project).
- **Want to see it first?** Open the [live demo](https://mdrbx.github.io/nerv-ui/) or browse all [18 examples](https://mdrbx.github.io/nerv-ui/examples/).

### `> USE_WITH_AN_AI_CODING_AGENT`

Install the canonical NERV-UI skill for your coding agent:

```bash
npx skills add https://github.com/mdrbx/nerv-ui --skill nerv-ui
```

The installer discovers supported agents and lets you choose where to install the skill. You can also [inspect NERV-UI on skills.sh](https://skills.sh/mdrbx/nerv-ui/nerv-ui) before installing it.

The skill tells an agent when NERV-UI fits, installs the real npm package, uses only exported components, and includes dashboard, terminal, and authentication recipes.

> **Try this prompt:** “Install `@mdrbx/nerv-ui` and build an accessible operations dashboard with `DataGrid`, `Gauge`, and `BarChart`; use original labels and respect reduced motion.”

<details>
<summary>Manual agent installation</summary>

Clone the repository and copy the canonical skill directory to your agent's user-level skill path:

```bash
git clone --depth 1 https://github.com/mdrbx/nerv-ui.git /tmp/nerv-ui-skill

# Codex
mkdir -p ~/.codex/skills
cp -R /tmp/nerv-ui-skill/skills/nerv-ui ~/.codex/skills/nerv-ui

# Hermes Agent
mkdir -p ~/.hermes/skills
cp -R /tmp/nerv-ui-skill/skills/nerv-ui ~/.hermes/skills/nerv-ui
```

Inside this repository, compatible agents can discover the same canonical source through [`.agents/skills/nerv-ui`](.agents/skills/nerv-ui) and [`.claude/skills/nerv-ui`](.claude/skills/nerv-ui).

</details>

### `> INSTALL_IN_A_REACT_PROJECT`

```bash
npm install @mdrbx/nerv-ui framer-motion
```

```tsx
import { Button, TerminalDisplay, Gauge } from "@mdrbx/nerv-ui";
import "@mdrbx/nerv-ui/styles.css";

export default function App() {
  return (
    <div className="bg-black min-h-screen p-8">
      <TerminalDisplay
        lines={[
          "MAGI SYSTEM v2.11",
          "> Initializing...",
          "> All systems online",
        ]}
        typewriter
        color="green"
      />
      <Gauge value={73} label="SYNC RATE" color="cyan" />
      <Button variant="danger" size="lg">
        INITIATE OVERRIDE
      </Button>
    </div>
  );
}
```

**Peer dependencies:** `react`, `react-dom`, `framer-motion`. Tailwind CSS is optional. NERV-UI is the useful middle ground between a style-only prompt and a bespoke CSS rebuild: you get typed, importable, tested component primitives plus working compositions.

<details>
<summary>Tailwind CSS preset (optional)</summary>

```js
// tailwind.config.js
import nervPreset from "@mdrbx/nerv-ui/tailwind.preset";

export default {
  presets: [nervPreset],
};
```

</details>

---

## `> WHY_NERV_UI`

- **Real React package:** `@mdrbx/nerv-ui` ships TypeScript declarations and package CSS—not a pasted stylesheet or a visual prompt.
- **Build from complete flows:** the [live examples](https://mdrbx.github.io/nerv-ui/examples/) cover dashboards, monitoring, forms, auth, content, and error states.
- **Agent-ready without lock-in:** one canonical `SKILL.md` steers compatible agents toward the published exports and documented recipes.
- **Accessible motion baseline:** interactive components and examples are built in React, and the project’s styling accounts for `prefers-reduced-motion`.

---

## `> WHAT_IS_NERV_UI`

NERV-UI is a **48-component React design system** published on npm for original CRT-era, command-center-inspired interfaces. Every pixel follows strict brutalist design rules:

- **`border-radius: 0`** nearly everywhere — sharp industrial angles only
- **NERV color palette** — black void, alert red, text orange, grid green, data cyan, magenta wave
- **Condensed uppercase typography** — Oswald, Barlow Condensed, Noto Serif JP
- **Monospace terminal text** — Fira Code for all data readouts
- **EVA title-card compositions** — staged 4:3 layouts for ceremonial episode/finale screens
- **CRT scanline overlay** — persistent retro phosphor effect
- **Monitor overlays and targeting rails** — MAGI/NERV-inspired screen framing for dashboards, dialogs, and launch decks
- **Animated hazard chevrons** — V-shaped stripe patterns for danger states
- **Interactive chart surfaces** — hover-reactive bars, slices, gauges, and status bands with tactical tooltip overlays
- **`prefers-reduced-motion`** — all animations respect accessibility settings

---

## `> COMPONENTS`

**48 components** across 7 categories. Full API reference in the [documentation](https://mdrbx.github.io/nerv-ui/docs).

| Category           | Components                                                                                                                                       |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Layout**         | `TargetingContainer`, `HexGridBackground`, `MonitorOverlay`, `Card`, `Accordion`, `Divider`, `Drawer`, `Breadcrumb`                               |
| **Forms**          | `Button`, `InputField`, `SelectMenu`, `Checkbox`, `Toggle`, `Textarea`, `RadioGroup`, `FileUpload`                                               |
| **Data Display**   | `TerminalDisplay`, `DataGrid`, `SyncProgressBar`, `SegmentDisplay`, `Badge`, `Skeleton`, `PilotCard`, `Pagination`                               |
| **Charts**         | `BarChart`, `Gauge`, `PieChart`, `SyncRatioChart`, `PhaseStatusStack`, `GradientStatusBar`                                                       |
| **Overlays**       | `SystemDialog`, `ClassifiedOverlay`, `TitleScreen`, `NervToastProvider`, `StatusStamp`, `Tooltip`, `DropdownMenu`                                |
| **Navigation**     | `NavigationTabs`, `EmergencyBanner`, `Stepper`                                                                                                   |
| **HUD / Military** | `TargetingReticle`, `SurveillanceGrid`, `PatternAlert`, `MagiSystemPanel`, `SeeleMonolith`, `CountdownTimer`, `WireframeLoader`, `ThemeProvider` |

> **[Browse all components →](https://mdrbx.github.io/nerv-ui/docs)**

---

## `> EXAMPLE_PAGES`

**18 production-ready example pages** showcasing real-world usage patterns. All responsive.

| Page                                                                           | Description                               |
| ------------------------------------------------------------------------------ | ----------------------------------------- |
| [**Command Center**](https://mdrbx.github.io/nerv-ui/)                          | NERV HQ main dashboard with live data     |
| [**Operations Dashboard**](https://mdrbx.github.io/nerv-ui/examples/dashboard)  | KPI cards, charts, gauges, operations log |
| [**Comms Terminal**](https://mdrbx.github.io/nerv-ui/examples/comms)            | Military chat interface with channels     |
| [**Dispatch Form**](https://mdrbx.github.io/nerv-ui/examples/form)              | Multi-field form with validation          |
| [**Intelligence Bulletin**](https://mdrbx.github.io/nerv-ui/examples/blog)      | Classified content feed with filtering    |
| [**Monitoring Station**](https://mdrbx.github.io/nerv-ui/examples/realtime)     | Real-time sensor data & charts            |
| [**Video Intercept Deck**](https://mdrbx.github.io/nerv-ui/examples/surveillance) | Aggressive surveillance wall with pilot channels, MAGI, and phase rails |
| [**Equipment Requisition**](https://mdrbx.github.io/nerv-ui/examples/inventory) | CRUD inventory management                 |
| [**Pilot Dossier**](https://mdrbx.github.io/nerv-ui/examples/pilots)            | Personnel profiles with sync history      |
| [**Mission Report**](https://mdrbx.github.io/nerv-ui/examples/report)           | After-action document template            |
| [**MAGI File System**](https://mdrbx.github.io/nerv-ui/examples/files)          | File browser with tree navigation         |
| [**SaaS Landing**](https://mdrbx.github.io/nerv-ui/examples/saas)               | Marketing page with pricing               |
| [**Library Landing**](https://mdrbx.github.io/nerv-ui/examples/landing)         | NERV-UI showcase page                       |
| [**Ceremonial Splash**](https://mdrbx.github.io/nerv-ui/examples/splash)        | Full-page EVA title-card splash screen    |
| [**Login**](https://mdrbx.github.io/nerv-ui/examples/auth/login)                | Authentication terminal                   |
| [**Register**](https://mdrbx.github.io/nerv-ui/examples/auth/register)          | Personnel registration                    |
| [**Help Center**](https://mdrbx.github.io/nerv-ui/examples/help)                | FAQ with knowledge base                   |
| [**Error 404**](https://mdrbx.github.io/nerv-ui/examples/error)                 | Signal lost page                          |

> **[Explore all examples →](https://mdrbx.github.io/nerv-ui/examples)**

---

## `> DESIGN_TOKENS`

```
COLOR             HEX        USAGE
─────────────────────────────────────────────
nerv-black         #000000    Background void
nerv-red           #FF0000    Emergency / alerts
nerv-orange        #FF9900    Primary text & UI
nerv-green         #00FF00    Terminal / grid lines
nerv-cyan          #00FFFF    Data readouts
nerv-magenta       #FF00FF    Waveform accents
nerv-lcd-green     #39FF14    LCD displays
nerv-amber         #FFAA00    Warning states
nerv-purple        #9933FF    Special indicators

TYPOGRAPHY        FAMILY                         USAGE
─────────────────────────────────────────────────────────
nerv-display       Oswald, Impact                 Headers & labels
nerv-mono          Fira Code, JetBrains Mono      Terminal & data
nerv-body          Barlow Condensed               Body text
nerv-title         Noto Serif JP, Playfair         Cinematic titles
```

---

## `> TECH_STACK`

| Technology    | Version | Role                              |
| ------------- | ------- | --------------------------------- |
| React         | 19      | Functional components with Hooks  |
| TypeScript    | 5.8     | Strict typing, all props exported |
| Tailwind CSS  | 4       | `@theme` design tokens            |
| Framer Motion | 12      | Animations & transitions          |

---

## `> CONTRIBUTING`

```bash
git clone https://github.com/mdrbx/nerv-ui.git
cd nerv-ui
npm install
npm run dev         # Dev server at localhost:3000
npm run build:lib   # Build the npm package
npm run test        # Run tests
npm run type-check  # TypeScript check
```

See [CONTRIBUTING.md](CONTRIBUTING.md) for component patterns and design rules.

---


## `> CREDITS AND INSPIRATION`

<p>NERV-UI is an independent fan-inspired open-source project. It is not affiliated with, endorsed by, or sponsored by the owners of Neon Genesis Evangelion or its related marks.</p>

<p>MADE WITH [REDACTED] BY <a href="https://github.com/mdrbx">mdrbx</a></p>


---


## `> LICENSE`

MIT License. See [LICENSE](./LICENSE).
