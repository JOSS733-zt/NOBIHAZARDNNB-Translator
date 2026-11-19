# Nobihazard NNB-Translation 使用說明

作者：JOSS ｜ 單一 exe ｜ 免安裝

## 支援引擎

| 引擎 | 資料 | 方式 |
|---|---|---|
| RPG Maker MV / MZ | `data\*.json` | 寫回資料，或安裝執行時對照外掛 |
| RPG Maker XP | `Data\*.rxdata` | 直接寫回 |
| RPG Maker VX | `Data\*.rvdata` | 直接寫回 |
| RPG Maker VX Ace | `Data\*.rvdata2` | 直接寫回 |

2000 / 2003（`.ldb`）暫不支援。

## 三步驟

1. **① 選擇遊戲**：選到含 `www` / `data` / `Data` 的那一層 → 「識別遊戲」
2. **② 翻譯設定**：選引擎 → 「測試引擎」確認可翻 → **③ 勾分區**
3. 「掃描文字」→「開始翻譯」→「寫回遊戲」（會先自動備份）

## 翻譯引擎（全部免 Key）

| 引擎 | 說明 |
|---|---|
| 微軟翻譯（預設） | `cn.bing.com`，直連；被限流就把併發調成 1 |
| MyMemory | 直連，每日約 5000 字元額度；最保留佔位令牌 |
| Google 免費介面 | 需代理 |

## 分區

勾哪幾個，就只掃描、只翻譯哪幾個：地圖事件 / 地圖名 / 公共事件 / 物品 / 技能 / 武器 / 防具 / 角色 / 狀態敵人 / 敵群 / 系統 / 其他。

取消勾選的列會從表格隱藏，也不會被翻譯。

## 檔案位置

```
<遊戲目錄>
├── translate\cache_<語言>.json   斷點快取
├── translate\glossary.txt        自訂術語
├── translate\對照表_*.html       原文/譯文對照
└── translate\backup_*\           寫回前備份
```

MV/MZ 另有 `data\TranslatePlus\` 與 `js\plugins\TranslatePlus.js`。

## 常見問題

- **雙擊閃退**：看程式目錄的 `startup.log` / `crash.log`
- **識別不到**：選到含 `data` / `Data` 的那層；`Game.rgss3a` 要先解包
- **回傳空內容**：被限流，併發改 1，等幾分鐘
- **狀態「複核」**：機翻丟了控制符，雙擊譯文修改
- **中文顯示方塊**（XP/VX/VA）：換 `Fonts\` 裡的的字體
- **改名 / 換語言**：編輯 `nnb.ini` 的 `name=` / `lang=`

## 授權

MIT。永久免費，不收費、不需要啟用。工具不含任何遊戲素材。
