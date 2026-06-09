# Note Pro

**浏览器里的 Typora** — 零安装、零配置，开箱即用的 Markdown 所见即所得编辑器。数据完全存储在本地，无后端、无账号、无隐私顾虑。


---

## 🎯 为什么选 Note Pro？

| 特性 | 说明 |
|------|------|
| 🖊️ **零学习成本** | 所见即所得，打字即时渲染，无需记住复杂语法 |
| 📂 **版本历史** | 自动快照，可视化 diff 对比，一键回滚到任意历史版本 |
| 🔒 **本地优先** | 数据完全存储在本地 IndexedDB / 文件系统，隐私安全 |
| 🌐 **零安装运行** | 纯浏览器，Chrome/Edge 直接打开即用，无需 Node/Python |
| 🎨 **5 种主题** | 浅色 / 深色 / 跟随系统 / GitHub 浅 / GitHub 深 |
| ⚡ **轻量快速** | 打包后仅 ~300KB，无任何外部依赖 |

---

## ✨ 功能特性

### 📝 所见即所得编辑
- 实时渲染 Markdown，**打字即出效果**
- `⌘B` 加粗 · `⌘I` 斜体 · `⌘⇧X` 删除线 · `⌘K` 链接 · `` ⌘` `` 行内代码
- 标题 1-3 级快捷键（`⌘1/2/3`）
- 有序列表、无序列表、引用块、代码块（语法高亮）
- 表格编辑：插入行/列、合并单元格、快捷键操作

### 📄 源码模式
- 按 `⌘/` 随时切换 Markdown 源码视图
- 源码模式下 `⌘S` 同步回渲染视图，blur 自动保存
- 完整保留所有 Markdown 语法标记

### 📂 文件管理
- **打开本地文件夹**：File System Access API，文件直接在本地读写
- **打开单个文件**：支持从任意位置打开 Markdown 文件
- 多标签页同时编辑
- 拖放导入：拖入 `.md` 文件或文件夹，自动解析文件树
- **自动保存**：可配置间隔（默认 30s），不必担心丢失更改

### 🕐 版本历史 ⭐
- 每次保存自动生成 Git 快照（基于 isomorphic-git）
- 历史记录面板：**可视化 diff 对比**，新增绿色、删除红色，一目了然
- **一键恢复**：点击任意历史版本，内容完整还原
- 支持撤销/重做（`⌘Z` / `⌘⇧Z`）

### 🎨 个性化
- **5 种主题**：浅色 / 深色 / 跟随系统 / GitHub Light / GitHub Dark
- 可调字号（12–32px）和行高（1.4–2.5）
- 专注模式：隐藏侧边栏，全屏写作
- 完整键盘快捷键支持

### 🌐 浏览器兼容
- **Chrome 86+ / Edge 86+**：完整功能（File System Access API）
- **Firefox / Safari**：内存模式 + IndexedDB 持久化（功能受限）

---

## 🚀 安装使用

### 🖥️ 桌面版（Note Pro）

> Tauri 打包的桌面客户端，支持 macOS / Windows / Linux。

**下载地址：** [GitHub Releases](https://github.com/bbroot/Note Pro/releases)

#### 🍎 macOS 安装说明

下载 `.dmg` 后：

1. 打开 `Note Pro.dmg`，把 **Note Pro.app** 拖到「应用程序」文件夹
2. 首次打开会在「启动台」里看到 Note Pro 图标，点击它
3. macOS 会弹出提示：「无法验证 Note Pro.app 是否包含恶意软件…」

**✅ 正常！这是没有 Apple 公证的开源软件的正常行为。** 按以下步骤打开：

<details>
<summary><strong>方式一（推荐）：系统设置里允许</strong></summary>

1. 关闭刚才的警告弹窗（点「取消」）
2. 打开「系统设置 → 隐私与安全性」，往下滑到最下方
3. 看到「Note Pro 已被阻止…」，点击「仍要打开」
4. 再次确认「打开」，之后就不会再弹了

</details>

<details>
<summary><strong>方式二：右键打开</strong></summary>

1. 在 Finder 里找到「应用程序 → Note Pro.app」
2. **右键**（或 Control + 点击）Note Pro.app
3. 在菜单里选「打开」
4. 弹窗点「打开」，以后直接双击就能打开了

</details>

<details>
<summary><strong>方式三：终端一键清除隔离属性</strong></summary>

```bash
xattr -cr /Applications/Note Pro.app
open /Applications/Note Pro.app
```

</details>

> 💡 VS Code、Obsidian 等开源软件在未购买 Apple Developer 账号前也是同样流程。

#### 🪟 Windows / 🐧 Linux

- **Windows**：下载 `.exe` 安装包，双击安装即可
- **Linux**：下载 `.AppImage` 或 `.deb`，给执行权限后运行

---

### 方式一：浏览器直接使用（推荐）

```bash
# 克隆仓库
git clone https://github.com/bbroot/Note Pro.git
cd Note Pro

# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 构建生产版本
npm run build
```

### 方式二：浏览器直接打开

构建后打开 `dist/index.html`，或使用任意静态服务器：

```bash
# Python
python3 -m http.server 3000

# Node.js
npx serve dist
```

### 方式三：零配置打包分发

```bash
npm run package
# 产物: note-pro-<version>-portable.zip (~300KB)
```

**macOS / Linux**: 解压后运行 `bash start.sh`
**Windows**: 双击 `start.bat` 或运行 `powershell -ExecutionPolicy Bypass -File start.ps1`

启动脚本自动检测环境（Node.js → Python → .NET），无需手动配置。

---

## 🛠 技术栈

| 层级 | 技术 | 用途 |
|------|------|------|
| 框架 | React 18 | UI 组件化 |
| 状态管理 | Zustand | 轻量全局状态 |
| 编辑器引擎 | **ProseMirror** | 所见即所得编辑核心 |
| Markdown 解析 | markdown-it + Shiki | 解析渲染 + 语法高亮 |
| 版本历史 | **isomorphic-git + IndexedDB** | 本地 Git 快照 |
| 样式 | Tailwind CSS | 原子化 CSS |
| 构建工具 | Vite | 快速构建 |

---

## ⌨️ 快捷键

### 文件操作
| 快捷键 | 功能 |
|--------|------|
| `⌘N` | 新建文件 |
| `⌘O` | 打开文件夹 |
| `⌘⇧O` | 打开单个文件 |
| `⌘S` | 保存文件 |
| `⌘⇧S` | 另存为 |
| `⌘W` | 关闭标签页 |
| `⌘E` | 导出 |

### 格式化
| 快捷键 | 功能 |
|--------|------|
| `⌘B` | 加粗 |
| `⌘I` | 斜体 |
| `⌘⇧X` | 删除线 |
| `` ⌘` `` | 行内代码 |
| `⌘K` | 插入链接 |
| `⌘1/2/3` | 标题 1/2/3 |
| `⌘0` | 正文 |
| `⌘/` | 切换源码模式 |

### 编辑
| 快捷键 | 功能 |
|--------|------|
| `⌘Z` | 撤销 |
| `⌘⇧Z` | 重做 |

---

## 📦 项目结构

```
note-pro/
├── src/
│   ├── components/
│   │   ├── Editor.tsx         # ProseMirror 编辑器 + 源码模式
│   │   ├── Toolbar.tsx        # 格式化工具栏
│   │   ├── Sidebar.tsx       # 递归文件树 + 拖放
│   │   ├── TabBar.tsx        # 多标签页
│   │   ├── HistoryPanel.tsx  # 版本历史 + diff 对比
│   │   └── SettingsPanel.tsx # 主题/字体/自动保存设置
│   ├── lib/
│   │   ├── filesystem.ts     # File System Access API 抽象层
│   │   ├── git.ts            # isomorphic-git 版本快照
│   │   ├── markdown.ts        # Markdown ↔ ProseMirror 双向转换
│   │   ├── schema.ts         # ProseMirror Schema（表格/删除线等）
│   │   └── editorView.ts      # 编辑器实例管理
│   ├── store/
│   │   └── editorStore.ts     # Zustand 全局状态（文件/标签/历史）
│   ├── App.tsx                # 根组件（拖放/快捷键/主题）
│   └── main.tsx               # 入口
├── start.sh / start.bat / start.ps1  # 跨平台一键启动
├── package.sh                 # 打包分发脚本
└── README.md
```

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'Add amazing feature'`)
4. 推送分支 (`git push origin feature/amazing-feature`)
5. 创建 Pull Request

---

## 📄 许可证

[MIT License](LICENSE) © 2026 Note Pro

---

## 🙏 致谢

- [ProseMirror](https://prosemirror.net/) — 所见即所得编辑框架
- [Typora](https://typora.io/) — 设计灵感
- [isomorphic-git](https://isomorphic-git.org/) — 纯 JavaScript Git 实现
