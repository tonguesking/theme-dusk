# Dusk — PolyCreator 主题

[![Release](https://img.shields.io/github/v/release/tonguesking/theme-dusk)](https://github.com/tonguesking/theme-dusk/releases/latest)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](LICENSE)

Dusk（黄昏）是一套 [PolyCreator](https://polycreator.si) 主题，包含一个浅色主题和一个配套的深色主题。

- **市场页面**：<https://polycreator.si/plugins/tonguesking.dusk>
- **插件 id**：`tonguesking.dusk`
- **类型**：纯数据主题（data-only），不含任何可执行代码

[English](#english) · [中文](#中文)

---

## 中文

### 主题一览

| 文件 | 主题 id | 外观 | 背景 / 文字 / 主色 |
|---|---|---|---|
| `theme.json` | `tonguesking.dusk` | 浅色 | 暖米色 `#faf6f1` / 深梅紫 `#2b2233` / 玫瑰红 `#a3456b` |
| `theme-dark.json` | `tonguesking.dusk:theme-dark` | 深色（继承 `builtin-dark`） | 深梅紫 `#1c1724` / 浅色文字 / 粉色 `#f08fb0` |

- 46 个颜色变量（`THEME_TOKENS`）全部设置，用的都是普通 hex 色值。
- 所有文字与背景的对比度（正文、主色、弱化文字、成功/警告/信息提示、侧边栏等）都达到 WCAG AA，即 ≥ 4.5:1。
- 节点生成中的光晕是一条从夕阳橙到玫瑰红、紫罗兰再到蓝色的渐变。

### 安装

开始前请先安装 PolyCreator 桌面端，从 <https://polycreator.si/download> 下载。主题不含代码，安装不会在你的电脑上运行任何程序。

#### 方式一：从网站一键安装（推荐）

1. 用浏览器打开 Dusk 的市场页面 <https://polycreator.si/plugins/tonguesking.dusk>。
2. 点 **「安装到 PolyCreator」**。浏览器会通过深链打开桌面端：

   ```
   polycreator://install?url=https%3A%2F%2Fgithub.com%2Ftonguesking%2Ftheme-dusk%2Freleases%2Flatest%2Fdownload%2Ftonguesking.dusk.zip
   ```

   如果浏览器询问"是否打开 PolyCreator"，选允许。
3. 桌面端会弹出原生确认框，显示名称、版本、来源 host（`github.com`）和信任级别。确认无误后点确认。
4. 桌面端从 GitHub Release 下载最新版 `tonguesking.dusk.zip`，用包里的 `integrity` 哈希校验文件，校验通过后安装。哈希不一致时会拒绝安装。
5. 安装完成后，按下文[「启用主题」](#启用主题)切换外观。

**点按钮没反应？**
- 先确认桌面端已经安装，并且至少打开过一次，这样系统才会登记 `polycreator://` 协议。
- 还是不行的话，复制按钮下方显示的下载链接，改用方式三「从 URL 安装」。

#### 方式二：在桌面端市场里安装

1. 打开桌面端的 **「市场」** 标签页。
2. 搜索 `Dusk` 或 `tonguesking`，点安装。

版本检查和完整性校验都在后台自动完成。

#### 方式三：从 URL 安装

在桌面端 **「插件管理 → 从 URL 安装」** 里粘贴下面这个永远指向最新版的链接：

```
https://github.com/tonguesking/theme-dusk/releases/latest/download/tonguesking.dusk.zip
```

想固定在某个版本，就用带版本号的链接，例如：

```
https://github.com/tonguesking/theme-dusk/releases/download/v0.1.0/tonguesking.dusk-0.1.0.zip
```

安装前会先显示 manifest 摘要，确认后才会安装。链接只接受 http(s)。

#### 方式四：本地安装（离线）

1. 在 [Releases](https://github.com/tonguesking/theme-dusk/releases) 页面下载 `tonguesking.dusk.zip`。
2. 在桌面端插件管理里选择本地安装，选中这个 zip 文件。

### 启用主题

1. 打开桌面端 **设置 → 外观**。
2. 在亮色主题里选 **Dusk**，在暗色主题里选 **Dusk（theme-dark）**。
3. 深浅模式选"跟随系统"时，两个主题会跟着系统自动切换。

自定义主题生效期间，强调色（accent）设置不起作用，看到的颜色都由主题决定。关掉主题后，强调色设置会恢复。

### 更新与卸载

- **更新**：作者发布新的 tag 后，从市场或网站安装的条目会检测到新版本，直接更新即可，不用卸载重装。
- **卸载**：在插件管理里卸载 Dusk。外观会回到内置主题。

### 常见问题

| 现象 | 处理 |
|---|---|
| 网站按钮没反应 | 确认已安装桌面端，或改用"从 URL 安装" |
| 提示完整性校验失败 | 下载不完整或文件被改过，重新安装；仍失败请[提 issue](https://github.com/tonguesking/theme-dusk/issues) |
| 主题整包被拒绝 | 有一个主题文件损坏时，整个主题包都会被拒绝，避免只加载一半；重装即可 |
| 选了 Dusk 但强调色没变 | 正常现象：主题生效期间强调色设置不起作用 |

---

## 开发与发布

### 目录结构

```
manifest.json      # 插件清单：id、版本、theme.files（无 main，无代码）
theme.json         # 浅色主题：appearance + 46 个 colors
theme-dark.json    # 深色主题：extends builtin-dark
scripts/pack.mjs   # 校验并打包
dist/              # 打包产物，作为 Release 附件上传
```

### 打包

```sh
npm run pack
```

它会依次完成这些事：
1. 用 `@polycreator/plugin-manifest` 校验 manifest 和两个主题文件。
2. 检查颜色变量是否齐全，以及文字与背景的对比度。
3. 按 `theme.files` 的顺序对主题文件计算 sha256，写入 `integrity`。
4. 生成 3 个 Release 附件：`tonguesking.dusk.zip`、`tonguesking.dusk-<version>.zip` 和 `manifest.json`。

### 发布新版本

1. 修改主题文件，同时把 `manifest.json` 和 `package.json` 里的 `version` 改成新版本号。
2. 运行 `npm run pack`，确认没有报错和警告。
3. 提交并打 tag，例如 `git tag v0.2.0 && git push --tags`。
4. 创建 GitHub Release，把 `dist/` 里的 3 个文件作为附件上传。

市场已经登记过这个仓库，以后发版只需要打 tag 和建 Release，不用再改 [poly-creator/plugins](https://github.com/poly-creator/plugins) 的登记。

---

## English

Dusk is a warm twilight theme family for [PolyCreator](https://polycreator.si): a soft rose-on-paper light theme (`tonguesking.dusk`) and a deep plum dark theme (`tonguesking.dusk:theme-dark`, extends `builtin-dark`). It is a data-only theme with no executable code. All 46 tokens are set, and every text/background pair meets WCAG AA (≥ 4.5:1).

### Install

You need the PolyCreator desktop app first: <https://polycreator.si/download>.

1. **From the website (recommended).** Open <https://polycreator.si/plugins/tonguesking.dusk> and click **Install to PolyCreator**. Your browser hands the app a `polycreator://install?url=…` deep link. The app shows a native confirmation with the name, version, source host and trust level, then downloads the latest release and verifies its `integrity` hash. If the button does nothing, make sure the app is installed and has been opened once, or use option 3.
2. **From the in-app marketplace.** Open the **Marketplace** tab, search for `Dusk`, and click install.
3. **From a URL.** Paste `https://github.com/tonguesking/theme-dusk/releases/latest/download/tonguesking.dusk.zip` into **Plugins → Install from URL**.
4. **Offline.** Download the zip from [Releases](https://github.com/tonguesking/theme-dusk/releases) and install it as a local package.

### Enable

Go to **Settings → Appearance**. Pick **Dusk** as the light theme and **Dusk (theme-dark)** as the dark theme. While a custom theme is active, the accent color setting is ignored.

### Build and release

Run `npm run pack`, which validates, computes integrity and writes `dist/`. Bump `version`, tag `vX.Y.Z`, and attach the 3 files in `dist/` to a GitHub Release. The marketplace picks up new tags automatically.

---

MIT © tonguesking
