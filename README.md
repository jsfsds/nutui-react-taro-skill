# NutUI React Taro Skill

An agent skill for building, reviewing, migrating, and troubleshooting Taro React mini-program pages with `@nutui/nutui-react-taro`.

This skill helps an AI coding agent:

- verify the current NutUI/Taro package versions before giving version-specific advice;
- choose NutUI React Taro components from product requirements;
- generate Taro React page code with mini-program-safe patterns;
- inspect local project dependencies and avoid package/version mismatches;
- troubleshoot setup, imports, icons, theme/style configuration, and Taro mini-program caveats.

Chinese README: [README.zh-CN.md](README.zh-CN.md)

## Why This Exists

NutUI React Taro moves quickly, and npm dist-tags, GitHub releases, docs, and a local project's lockfile may not always point to the same version. This skill is designed to make the agent check the real project and current upstream metadata first, then produce component plans and code that match the installed version.

## Install

From the skills CLI, after this repository is public:

```bash
npx skills add jsfsds/nutui-react-taro-skill@nutui-react-taro
```

Manual install:

Copy this folder into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R nutui-react-taro ~/.codex/skills/
```

On Windows PowerShell:

```powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.codex\skills"
Copy-Item -Recurse -Force ".\nutui-react-taro" "$env:USERPROFILE\.codex\skills\"
```

If you cloned this repository directly, make sure the folder name inside `skills` is exactly:

```text
nutui-react-taro
```

## Usage

Invoke the skill explicitly in Codex:

```text
Use $nutui-react-taro to design a Taro React mini-program order list page with NutUI components.
```

Example prompts:

```text
Use $nutui-react-taro. Based on this requirement, choose suitable NutUI components and generate the Taro React page code: a product detail page with SKU selection, coupons, quantity stepper, and fixed bottom actions.
```

```text
Use $nutui-react-taro to review my Taro page and fix NutUI component imports, event handlers, and mini-program compatibility issues.
```

```text
Use $nutui-react-taro to check whether my project should install @tarojs/plugin-html and how to configure NutUI styles.
```

## Test

Validate the skill structure with the official skill creator validator:

```bash
python /path/to/skill-creator/scripts/quick_validate.py /path/to/nutui-react-taro
```

Check live package metadata:

```bash
cd nutui-react-taro
node scripts/check-current-packages.js
```

The script queries npm metadata for:

- `@nutui/nutui-react-taro`
- `@nutui/icons-react-taro`
- `@tarojs/taro`
- `@tarojs/components`
- `@tarojs/plugin-html`

## Contents

```text
nutui-react-taro/
  SKILL.md
  agents/openai.yaml
  references/component-selection.md
  references/official-sources.md
  references/setup-and-patterns.md
  scripts/check-current-packages.js
```

## License

MIT
