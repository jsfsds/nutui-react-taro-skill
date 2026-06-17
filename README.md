<a id="readme-en"></a>

# NutUI React Taro Skill

<p align="right">
  <strong>English</strong> | <a href="#readme-zh-cn">简体中文</a>
</p>

An agent skill for building, reviewing, migrating, and troubleshooting Taro React mini-program pages with `@nutui/nutui-react-taro`.

This skill helps an AI coding agent:

- verify the current NutUI/Taro package versions before giving version-specific advice;
- choose NutUI React Taro components from product requirements;
- generate Taro React page code with mini-program-safe patterns;
- inspect local project dependencies and avoid package/version mismatches;
- troubleshoot setup, imports, icons, theme/style configuration, and Taro mini-program caveats.

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

---

<a id="readme-zh-cn"></a>

# NutUI React Taro Skill

<p align="right">
  <a href="#readme-en">English</a> | <strong>简体中文</strong>
</p>

这是一个面向 Codex/AI coding agent 的本地 skill，用来辅助开发、审查、迁移和排查基于 `@nutui/nutui-react-taro` 的 Taro React 小程序页面。

它可以帮助 agent：

- 在给出版本相关建议前，先查询当前 NutUI/Taro 包版本；
- 根据产品需求选择合适的 NutUI React Taro 组件；
- 生成符合 Taro React 和小程序约束的页面代码；
- 检查本地项目依赖，避免 React/Vue 包、Taro 版本、插件配置混用；
- 排查安装、导入、图标、主题样式、`@tarojs/plugin-html`、小程序兼容性等问题。

## 为什么需要这个 Skill

NutUI React Taro 更新比较快，npm dist-tags、GitHub releases、官方文档和本地项目 lockfile 有时并不完全一致。这个 skill 的核心设计不是“死记某一天的文档”，而是强制 agent 先查本地项目和当前上游信息，再根据实际版本做组件选型和代码生成。

## 安装

仓库公开后，可以通过 skills CLI 安装：

```bash
npx skills add jsfsds/nutui-react-taro-skill@nutui-react-taro
```

也可以手动安装：

把该目录复制到 Codex skills 目录：

```powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.codex\skills"
Copy-Item -Recurse -Force ".\nutui-react-taro" "$env:USERPROFILE\.codex\skills\"
```

如果你是从 GitHub clone 下来的，请确保放进 skills 目录后的文件夹名就是：

```text
nutui-react-taro
```

## 使用方式

在 Codex 里显式调用：

```text
Use $nutui-react-taro to design a Taro React mini-program order list page with NutUI components.
```

中文也可以这样问：

```text
使用 $nutui-react-taro，根据我的需求选择 NutUI 组件并生成 Taro React 小程序页面代码：商品详情页，需要 SKU 选择、优惠券、数量步进器和底部固定购买按钮。
```

```text
使用 $nutui-react-taro，帮我审查这个 Taro 页面，修复 NutUI 组件导入、事件处理和小程序兼容性问题。
```

```text
使用 $nutui-react-taro，检查我的项目是否需要安装 @tarojs/plugin-html，以及 NutUI 样式应该怎么配置。
```

## 如何测试

验证 skill 结构：

```bash
python /path/to/skill-creator/scripts/quick_validate.py /path/to/nutui-react-taro
```

检查实时 npm 包信息：

```bash
cd nutui-react-taro
node scripts/check-current-packages.js
```

该脚本会查询：

- `@nutui/nutui-react-taro`
- `@nutui/icons-react-taro`
- `@tarojs/taro`
- `@tarojs/components`
- `@tarojs/plugin-html`

## 目录结构

```text
nutui-react-taro/
  SKILL.md
  agents/openai.yaml
  references/component-selection.md
  references/official-sources.md
  references/setup-and-patterns.md
  scripts/check-current-packages.js
```

## 许可证

MIT
