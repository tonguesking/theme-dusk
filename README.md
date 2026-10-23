# Dusk — a PolyCreator theme

Warm twilight theme family for [PolyCreator](https://polycreator.si).

| File | Theme id | Appearance |
|---|---|---|
| `theme.json` | `tonguesking.dusk` | light — warm paper background, rose primary `#a3456b` |
| `theme-dark.json` | `tonguesking.dusk:theme-dark` | dark — deep plum `#1c1724`, pink primary `#f08fb0` (extends `builtin-dark`) |

- Data-only theme (no JS). All 46 `THEME_TOKENS` set with plain hex colors.
- Text/background pairs (foreground, primary, muted, success, warning, info, sidebar…) meet WCAG AA (≥ 4.5:1).
- Generating-node halo runs sunset orange → rose → violet → blue.

## 中文

Dusk（黄昏）主题：浅色版是暖米色纸面配玫瑰红主色，深色版是深梅紫背景配粉色主色。纯数据主题，不含任何代码；所有文字与背景的对比度都达到 WCAG AA。

## Install

PolyCreator → Plugins/Themes marketplace → **Dusk**, or install from URL:
`https://github.com/tonguesking/theme-dusk/releases/latest/download/tonguesking.dusk.zip`

## Build

```sh
npm run pack   # validates, computes integrity, writes dist/
```

MIT © tonguesking
