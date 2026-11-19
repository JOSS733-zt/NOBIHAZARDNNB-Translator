# Nobihazard NNB-Translation

> 一个给 RPG Maker 游戏批量汉化的 Windows 工具 · 单文件 · 免安装 · 免 Key · 多语言界面

![platform](https://img.shields.io/badge/platform-Windows%207%2B-0078D6?style=flat-square)
![.NET](https://img.shields.io/badge/.NET-Framework%204.x-512BD4?style=flat-square)
![size](https://img.shields.io/badge/size-~360%20KB-lightgrey?style=flat-square)
![license](https://img.shields.io/badge/license-MIT-green?style=flat-square)
![lang](https://img.shields.io/badge/UI-6%20languages-orange?style=flat-square)

扫描游戏里的全部文本 → 机器翻译 → 写回原文件；写回前自动备份，随时可一键还原。

<img src="assets/logo.png" width="420" alt="Nobihazard NNB-Translation">

---

## 目录

- [支持的游戏引擎](#支持的游戏引擎)
- [功能特性](#功能特性)
- [翻译引擎](#翻译引擎)
- [翻译库（词库）](#翻译库词库)
- [下载与使用](#下载与使用)
- [常见问题](#常见问题)
- [注意事项](#注意事项)
- [免责声明](#免责声明)
- [许可](#许可)
- [致谢](#致谢)

---

## 支持的游戏引擎

| 引擎 | 数据格式 | 支持 | 写回方式 |
|---|---|:---:|---|
| **RPG Maker MV** | JSON（`www/data/*.json`） | ✅ | 直接写回 |
| **RPG Maker MZ** | JSON（`data/*.json`） | ✅ | 直接写回 |
| **RPG Maker XP** | Ruby Marshal（`.rxdata`） | ✅ | 直接写回 |
| **RPG Maker VX** | Ruby Marshal（`.rvdata`） | ✅ | 直接写回 |
| **RPG Maker VX Ace** | Ruby Marshal（`.rvdata2`） | ✅ | 直接写回 |
| RPG Maker 2000 / 2003 | LCF（`.ldb`） | ❌ | 暂不支持 |

> 支持范围：数据库（物品、技能、装备、角色、状态、敌人）、地图事件、公共事件、系统文本。
> 脚本里写死的文本、打包在 `Game.rgss3a` 里的内容**不在扫描范围**。

---

## 功能特性

- **一键扫描**：自动识别引擎与数据目录，提取全部可翻译文本
- **按分区筛选**：地图事件 / 地图名 / 公共事件 / 物品 / 技能 / 武器 / 防具 / 角色 / 状态 / 敌人 / 系统 / 其他，可单独勾选
- **控制符保护**：`\C[2]`、`\N[1]`、`%1`、`{...}` 等占位符不会被翻译破坏
- **术语表**：内置 195 条 RPG 术语，保证「勇者」「魔法」等译名统一
- **断点续译**：翻译结果写入缓存，中断后重开接着翻，不重复消耗额度
- **自动备份**：写回前备份到 `translate/backup_*`，可一键还原
- **对照表**：可安装对照插件（MV/MZ），游戏内原文与译文并列显示
- **导出 HTML**：导出带原文/译文的对照表，方便校对
- **六语言界面**：简体中文 / 繁體中文 / English / 日本語 / 한국어 / Tiếng Việt，可随时切换
- **单文件**：一个 exe，无需安装、无需运行库（.NET Framework 4.x 为 Windows 自带）

---

## 翻译引擎

全部**免 Key**、免注册，不依赖任何 AI 服务：

| 引擎 | 大陆直连 | 需代理 | 说明 |
|---|:---:|:---:|---|
| 微软翻译（Bing） | ✅ | — | 质量最好，默认引擎 |
| MyMemory | ✅ | — | 匿名每日额度约 5000 字符 |
| Google | ❌ | ✅ | 质量好，需要能访问 Google |

> 引擎列表是实测可用的最小集合。其他公开接口（Yandex、LibreTranslate、Papago、搜狗等）经验证均不可用或已失效，没有放进来凑数。

---

## 翻译库（词库）

一张**原文 → 译文**的对照表，本地存储，与引擎无关：

- 内置基础库 **215 条**日→中（嵌在 exe 内）
- 用户库放在 `%APPDATA%\NNB-Translation\lib\`，可放任意多个文件
- 菜单：**帮助 → 翻译库 → 导入 / 打开目录 / 查看条目数**

**格式**（三种都认，UTF-8）：

```
勇者	勇者          ← Tab 分隔（推荐）
魔王=魔王            ← 等号
"王女","公主"        ← CSV
# 以 # 或 ; 开头是注释
```

扩展名支持 `.tsv` / `.txt` / `.csv` / `.json`。

**优先级**：整条命中 → 直接用库里的译文，不联网、不消耗额度；部分命中 → 库里的词替换，其余交给引擎。

---

## 下载与使用

### 下载

到 [Releases](../../releases) 页面下载最新的 `Nobihazard NNB-Translation.exe`。

- 单文件，约 360 KB
- 不需要安装，放到任意文件夹双击即可
- 首次运行会显示使用条款，选择语言并同意后进入主界面

### 三步汉化

1. **选游戏**：点「选择目录」，选到包含 `www` / `data` / `Data` 的**那一层**
2. **识别**：点「识别游戏」，确认引擎识别正确
3. **跑流程**：`扫描文本` → `开始翻译` → `写回游戏`

进度和结果都在底部日志里，出错会标红。

### 界面语言

**帮助 → 语言 / Language**，六选一，切换后立即生效。

### 配置文件

存放在 `%APPDATA%\NNB-Translation\`，不写程序目录（所以放哪都能跑，不需要管理员权限）：

| 文件 | 内容 |
|---|---|
| `nnb.ini` | 软件名、界面语言、条款同意状态 |
| `lib\*.tsv` | 翻译库 |
| `startup.log` / `crash.log` | 运行日志，反馈问题时可附上 |

---

## 常见问题

**Q：写回后游戏打不开 / 文本乱码怎么办？**
写回前会自动备份到游戏目录的 `translate\backup_*`。点「还原备份」即可恢复。建议首次使用前自己也复制一份游戏目录。

**Q：翻译到一半断了怎么办？**
重新打开，选同一个游戏，直接点「开始翻译」——已翻译的会从缓存读取，不会重翻。

**Q：能翻译脚本里的文本吗？**
不能。本工具只处理数据文件（JSON / rxdata 等），脚本里写死的字符串抓不到。

**Q：支持 RPG Maker 2000 / 2003 吗？**
暂不支持（LCF 二进制格式，解析器未实现）。

**Q：为什么杀毒软件报毒？**
exe 用自签名证书签名（发布者显示「未知」），部分杀软对自签名 + 写文件的程序比较敏感。源码在本仓库，可自行编译。

**Q：能翻译商业游戏吗？**
请先确认你所在国家或地区的法律是否允许，以及你是否拥有该游戏的合法副本。详见 [使用条款](TERMS.md)。

---

## 注意事项

- **先备份**：程序会自动备份，但建议自己也留一份原始游戏目录
- **不要改系统目录**：把 exe 放在普通文件夹即可，别放 `Program Files`
- **限流**：微软翻译并发太高会被限流，遇到失败把「并发」调成 1
- **首次运行**：需要同意使用条款，条款内容 6 种语言都提供
- **仅供学习与个人使用**：请勿用于传播盗版或未经授权的商业汉化

---

## 免责声明

本工具为个人作品，与 Gotcha Gotcha Games、KADOKAWA、微软等公司**无任何关联**。
`RPG Maker` 等名称是其各自权利人的商标，此处仅用于说明兼容性。

**游戏文件是否允许解包、修改、翻译，取决于你所在国家或地区的法律，以及该游戏的使用协议。**
使用者应自行确认行为合法，并对使用后果负责。作者不对因使用本工具产生的任何直接或间接损失承担责任。

完整条款见 [TERMS.md](TERMS.md)。

---

## 许可

源代码以 [MIT License](LICENSE) 发布，可自由使用、修改、再发布（需保留版权声明）。

---

## 编译

不需要 Visual Studio，也不需要 .NET SDK，用 Windows 自带的 `csc.exe` 即可：

```powershell
# 仓库根目录执行
powershell -ExecutionPolicy Bypass -File build.ps1
# 编译 + 跑单元测试
powershell -ExecutionPolicy Bypass -File build.ps1 -Test
```

产物在 `bin\RMTranslate.exe`。

要求：Windows + .NET Framework 4.x（Win7 及以上自带）。源码使用 **C# 5** 语法，请勿引入 C# 6+ 特性。

## 文档

| 语言 | 使用说明 | 引擎说明 |
|---|---|---|
| 简体中文 | [README.zh-CN](docs/README.zh-CN.md) | [RGSS.zh-CN](docs/RGSS.zh-CN.md) |
| 繁體中文 | [README.zh-TW](docs/README.zh-TW.md) | [RGSS.zh-TW](docs/RGSS.zh-TW.md) |
| English | [README.en](docs/README.en.md) | [RGSS.en](docs/RGSS.en.md) |
| 日本語 | [README.ja](docs/README.ja.md) | [RGSS.ja](docs/RGSS.ja.md) |
| 한국어 | [README.ko](docs/README.ko.md) | [RGSS.ko](docs/RGSS.ko.md) |
| Tiếng Việt | [README.vi](docs/README.vi.md) | [RGSS.vi](docs/RGSS.vi.md) |

---

## 致谢

- 作者：**JOSS**
- 内置术语表参考了 RPG Maker 社区通用译法
- 感谢所有反馈问题与提供游戏样本的测试者

---

<details>
<summary><b>English</b></summary>

### Nobihazard NNB-Translation

A single-file Windows tool for batch-localizing RPG Maker games (MV / MZ / XP / VX / VX Ace).
Scans all translatable text, machine-translates it, and writes it back — with automatic backup and one-click restore.

- **No installation, no API key, ~360 KB single exe**
- **6-language UI**: 简体中文 / 繁體中文 / English / 日本語 / 한국어 / Tiếng Việt
- **Engines**: Microsoft (Bing), MyMemory, Google — all keyless
- **Translation library**: local TSV/CSV dictionary, checked before any network call
- **Automatic backup** before writing back; resume-safe translation cache
- Licensed under **MIT**

Download from [Releases](../../releases), run the exe, pick your game folder, scan → translate → write back.

See [TERMS.md](TERMS.md) for the full disclaimer.

</details>
