<div align="center">
  <img src="logo.png" alt="Design Engine" width="140" />

# ▓▓ DESIGN ENGINE ▓▓

`[ vague idea :: adaptive interview :: design direction :: reusable prompt ]`

[![version](https://img.shields.io/badge/version-1.0.0-10b981?style=flat-square)](.claude-plugin/plugin.json)
[![format](https://img.shields.io/badge/format-agent_skill-10b981?style=flat-square)](https://agentskills.io)
[![license](https://img.shields.io/badge/license-GPL--3.0-10b981?style=flat-square)](LICENSE)

</div>
<br/>

```text
INTAKE → DECIDE → DIRECTION → PROMPT → BUILD NOTES
```

An Agent Skill that turns *"I need a ___ but don't know how it should
look"* into a concrete interface direction. It asks only for what's
missing — never a fixed questionnaire — and hands back a prompt you can
reuse in any generation or implementation tool.

<br/>

### ▸ install

```text
npx skills add jonaskahn/design-engine       # this project
npx skills add jonaskahn/design-engine -g -y # every project
```

Claude Code native marketplace:

```text
/plugin marketplace add jonaskahn/design-engine
/plugin install design-engine@design-engine
```

Either path installs [`skills/design-engine`](skills/design-engine/SKILL.md)
— or drop that folder into any skills directory by hand, no build step, no
dependencies.

<br/>

### ▸ usage

No command, no flags. Just describe what you're building.

> Help me design a landing page for a privacy-focused calendar app.
> Freelancers, main action is starting a trial, should feel calm not techy.

What happens next:

```text
1. keeps every fact already in your request
2. asks only the missing, consequential decisions — grouped, 3-6 per turn
3. routes to ONE experience type below, plus at most one variant
4. hands back: Selected UI Direction · Final Prompt · Build Notes
```

<br/>

#### ▸ experience types — auto-routed, pick one

| type | for |
|---|---|
| `personal` | portfolios, resumes, personal sites |
| `marketing` | landing pages, product sites, conversion pages |
| `application-ui` | dashboards, admin panels, internal tools |
| `ecommerce` | storefronts, marketplaces, real estate, job boards, directories |
| `content-docs` | blogs, docs, knowledge bases, changelogs |
| `mobile-app` | native / hybrid app screens |
| `ai-chat` | chat, assistant, agent interfaces |
| `email-template` | campaign, newsletter, transactional email |

`redesign` isn't a type of its own — say *"redesign my ___"* and it
overlays onto whichever type above matches the surface.

#### ▸ variants — layered on a type, at most one

- `event-page`, `nonprofit-donation`, `booking` → on `marketing`
- `saas-onboarding` → on `application-ui` or `marketing`
- `community-social` → on `application-ui`

#### ▸ always asked vs. only when it matters

- **theme** (light / dark / both) — every intake
- **accessibility target**, **localization / RTL** — only when the
  request signals it (regulated, enterprise, EU, multi-language,
  non-Latin script); otherwise a stated default is assumed, no extra
  questions

<br/>

### ▸ what it won't do

- invent copy, prices, testimonials, metrics, or brand assets — missing
  ones stay labeled placeholders
- send secrets, private URLs, or customer data into an external prompt
  without you saying so
- ship production code — output is a direction and a prompt, not a build

<br/>

### ▸ layout

```text
design-engine/
├── .claude-plugin/          plugin + marketplace manifests
└── skills/design-engine/
    ├── SKILL.md             entrypoint: workflow + routing
    └── references/          loaded on demand, one type at a time
        ├── shared-intake.md
        ├── output-contract.md
        ├── <experience-type>.md  × 8
        ├── redesign.md
        └── variants/         × 5
```
