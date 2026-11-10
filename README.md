# W32-SKILL

A Claude Code plugin marketplace for building and reviewing skills.

## Install

```
/plugin marketplace add w64xp/W32-SKILL
/plugin install w32-skill-tools@w32-skill
```

## Plugins

| Plugin | Skills | What it does |
| --- | --- | --- |
| `w32-skill-tools` | `w32-skill-builder` | Guides you step by step through creating a new skill |
| | `w32-skill-review` | Rewrites a skill in tighter wording with identical behavior and lists every change |

## Usage

```
/w32-skill-builder
/w32-skill-review
```

Or just describe what you want, for example "create a skill" or "review this skill".

## Update

```
/plugin marketplace update w32-skill
```

## Add a new skill

1. Create `plugins/<plugin>/skills/<skill-name>/SKILL.md` with `name` and `description` in the frontmatter.
2. Bump `version` in that plugin's `plugin.json` and in `marketplace.json`.
3. Commit and push.

## Add a new plugin

1. Create `plugins/<plugin-name>/.claude-plugin/plugin.json` and a `skills/` folder.
2. Add an entry to `.claude-plugin/marketplace.json`.

## Test locally

```
/plugin marketplace add ./W32-SKILL
/plugin install w32-skill-tools@w32-skill
```

## License

MIT
