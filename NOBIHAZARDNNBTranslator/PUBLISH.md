# GitHub 发布指南

按顺序做一遍即可，大约 10 分钟。

---

## 1. 创建仓库

1. 打开 https://github.com/new
2. **Repository name**：`NNB-Translation`
3. **Description**（复制这段）：

   ```
   RPG Maker 游戏批量汉化工具 | 单文件 · 免安装 · 免 Key · 支持 MV/MZ/XP/VX/VX Ace · 6 语言界面
   ```

4. 勾 **Public**
5. **不要**勾 "Add a README file"（我们要传自己的）
6. 点 **Create repository**

## 2. 上传文件

把本 `repo` 目录**里面的全部内容**传到仓库根目录（不是把 repo 文件夹本身传上去）：

```
NNB-Translation/
├── README.md          ← 主页
├── LICENSE            ← MIT
├── TERMS.md           ← 使用条款 / 免责声明
├── CONTRIBUTING.md
├── CHANGELOG.md
├── .gitignore
├── assets/            ← 图标、签名
└── docs/              ← 6 语言说明 + RGSS 指南
```

**不要上传**：`bin/`、`dist/`、`*.exe`、`signing/`（.gitignore 已排除）。

命令行方式：

```bash
git init
git add .
git commit -m "Initial commit: NNB-Translation v1.5.0"
git branch -M main
git remote add origin https://github.com/你的用户名/NNB-Translation.git
git push -u origin main
```

## 3. 设置 Topics（很重要，影响被搜到）

仓库首页右上角 ⚙️ **Settings** 旁边点 **Topics**，填入：

```
rpgmaker  rpg-maker  translation  localizaton  translator  mv  mz  vx-ace  xp  windows  csharp  winforms  chinese  game-tools
```

## 4. 发布 Release（放 exe）

1. 右侧 **Releases** → **Create a new release**
2. **Tag**：`v1.5.0` → 点 "Create new tag"
3. **Title**：`v1.5.0 — 首个公开版本`
4. **描述**（复制）：

   ```markdown
   ## 下载

   下载下方 Assets 里的 `Nobihazard NNB-Translation.exe`（单文件，免安装）。

   ## 支持

   - RPG Maker MV / MZ（JSON）
   - RPG Maker XP / VX / VX Ace（Ruby Marshal）

   ## 功能

   - 一键扫描 → 翻译 → 写回，写回前自动备份
   - 控制符保护（\C[2]、\N[1]、%1 等）
   - 195 条内置术语 + 可导入的翻译库
   - 断点续译、备份还原、HTML 对照表
   - 6 语言界面：简中 / 繁中 / EN / 日 / 韩 / 越

   ## 翻译引擎（全部免 Key）

   微软翻译 · MyMemory · Google

   ## 注意

   - 首次运行需同意使用条款（6 语言）
   - 配置存放在 `%APPDATA%\NNB-Translation\`，无需管理员权限
   - 请先备份游戏目录
   ```

5. **Attach binaries**：拖入 `Nobihazard NNB-Translation.exe`
6. 勾 **Set as the latest release** → **Publish release**

## 5. 仓库简介（About）

首页右侧 **About** → ⚙️ 编辑：

- **Description**：同上面第 1 步
- **Website**：留空
- 勾选 **Releases**、**License**（会自动读取 LICENSE）

---

## 6. 发布前自查清单

- [ ] `README.md` 里的 `assets/logo.png` 能正常显示
- [ ] LICENSE 是 MIT，作者写成你的名字
- [ ] `TERMS.md` 没有出现任何国家/地区名称
- [ ] 仓库里没有 `*.exe`、`signing/`、`nnb.ini`、日志
- [ ] Release 里 exe 能下载、能运行
- [ ] Topics 填了 10 个以上

---

## 后续更新流程

```bash
# 改完代码后
powershell -ExecutionPolicy Bypass -File build.ps1 -Test
# 更新 CHANGELOG.md 和 docs/CHANGELOG.*.md
git add .
git commit -m "v1.5.1: 修复 xxx"
git push
# 然后去 Releases 建新 tag v1.5.1，附上新 exe
```
