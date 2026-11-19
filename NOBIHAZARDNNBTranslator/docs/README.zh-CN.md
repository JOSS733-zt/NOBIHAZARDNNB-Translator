# Nobihazard NNB-Translation 使用说明

作者：JOSS ｜ 单个 exe ｜ 免安装

## 支持引擎

| 引擎 | 数据 | 方式 |
|---|---|---|
| RPG Maker MV / MZ | `data\*.json` | 写回数据，或装运行时对照插件 |
| RPG Maker XP | `Data\*.rxdata` | 直接写回 |
| RPG Maker VX | `Data\*.rvdata` | 直接写回 |
| RPG Maker VX Ace | `Data\*.rvdata2` | 直接写回 |

2000 / 2003（`.ldb`）暂不支持。

## 三步走

1. **① 选择游戏**：选到含 `www` / `data` / `Data` 的那一层 → 「识别游戏」
2. **② 翻译设置**：选引擎 → 「测试引擎」确认能翻 → **③ 勾分区**
3. 「扫描文本」→「开始翻译」→「写回游戏」（先自动备份）

## 翻译引擎（全部免 Key）

| 引擎 | 说明 |
|---|---|
| 微软翻译（默认） | `cn.bing.com`，国内直连；被限流就把并发调成 1 |
| MyMemory | 国内直连，每天约 5000 字符额度；最保占位令牌 |
| Google 免费接口 | 大陆需代理 |

## 分区

勾选哪几个，就只扫描、只翻译哪几个：地图事件 / 地图名 / 公共事件 / 物品 / 技能 / 武器 / 防具 / 角色 / 状态敌人 / 敌群 / 系统 / 其他。

取消勾选的行会从表格隐藏，也不会被翻译。

## 文件位置

```
<游戏目录>
├── translate\cache_<语言>.json   断点缓存
├── translate\glossary.txt        自定义术语
├── translate\对照表_*.html       原文/译文对照
└── translate\backup_*\           写回前备份
```

MV/MZ 另有 `data\TranslatePlus\` 与 `js\plugins\TranslatePlus.js`。

## 常见问题

- **双击闪退**：看程序目录的 `startup.log` / `crash.log`
- **识别不到**：选到含 `data` / `Data` 的那层；`Game.rgss3a` 要先解包
- **返回空内容**：被限流，并发改 1，等几分钟
- **状态「复核」**：机翻丢了控制符，双击译文改
- **中文显示方块**（XP/VX/VA）：换 `Fonts\` 里的字体
- **改名 / 换语言**：编辑 `nnb.ini` 的 `name=` / `lang=`

## 许可

MIT。永久免费，不收费、不需要激活。工具不含任何游戏素材。
