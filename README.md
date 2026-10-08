# 💣 网页极简扫雷 (Minesweeper Web)

<p align="center">
  <img src="https://img.shields.io/badge/Language-HTML5%20%7C%20CSS3%20%7C%20JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/Dependencies-Zero-success?style=flat-square" alt="Zero Dependencies" />
  <img src="https://img.shields.io/badge/Responsive-Mobile%20%26%20Desktop-blue?style=flat-square" alt="Responsive" />
  <img src="https://img.shields.io/badge/License-MIT-orange?style=flat-square" alt="MIT License" />
</p>

<p align="center">
  一款现代纯原生、极简质感、全平台自适应的 Web 扫雷游戏。<br>
  开箱即用，零构建依赖，支持移动端触屏与桌面端高效双击操作。
</p>

<p align="center">
  👉 <b><a href="https://kai-shekk.github.io/minesweeper/">【立即在线试玩 (Play Online)】</a></b> 👈
</p>

---

## ✨ 核心特性

- 🛡️ **首击安全机制 (Safe First Click)**：开局第一击保证绝不踩雷！若棋盘空间充足，第一击周围 8 格也均为安全区域，告别开局被秒杀的挫败感。
- ⚡ **智能连锁与快速翻开 (Flood Fill & Chording)**：
  - 点击空白格时自动连环扩散翻开周围安全区域。
  - **双击扩展（Chording）**：点击已翻开的数字，当其周围插旗数与数字匹配时，一键快速翻开周边剩余未标记格子。
- 🎯 **多档难度与自由定制**：
  - **初级**：9 × 9 网格，10 颗地雷
  - **中级**：16 × 16 网格，40 颗地雷
  - **高级**：16 × 30 网格，99 颗地雷
  - **自定义**：行数（5~30）、列数（5~40）、地雷数量随心配置
- 📱 **全平台自适应与移动端优化**：
  - 动态计算视口，格子大小自适应不同屏幕尺寸。
  - **移动端长按插旗**：长按 400ms 快速插旗/拔旗，并配备移动设备触觉震动反馈（Haptic Feedback）。
- 🏆 **最佳纪录持久化**：内置计时器与地雷计数器，各官方难度独立记录最优通关时间（自动保存在本地 `localStorage`）。
- 🎨 **清爽现代设计**：
  - 告别经典灰白拟物风，采用柔和清爽的浅色现代莫兰迪配色与圆角微阴影质感。
  - 状态表情实时反馈：🙂 正常 · 😮 翻开中 · 😵 踩雷失败 · 😎 胜利通关。
  - 内置趣味踩雷文案彩蛋。

---

## 🎮 操作指南

### 🖥️ 桌面端 (Desktop)

| 操作方式 | 功能说明 |
| :--- | :--- |
| **鼠标左键单击** | 翻开格子；若点击已翻开的数字，可触发周边快速展开 (Chording) |
| **鼠标右键单击** | 在未翻开格子上插旗 🚩 或取消标记 |
| **鼠标长按未松开** | 上方面部表情切换为 😮 紧张状态 |
| **键盘按键 `R`** | 快速重新开始当前难度游戏 |
| **点击状态表情** | 重置并重新开始一局新游戏 |

### 📱 移动触屏端 (Mobile)

| 操作方式 | 功能说明 |
| :--- | :--- |
| **轻触点击** | 翻开格子 / 点击数字快速翻开周边 |
| **长按 400ms** | 切换插旗 🚩 / 取消标记（支持轻度震动提示） |
| **双指缩放** | 页面支持全视口自适应，平滑滚动 |

---

## 🛠️ 技术实现

- **单文件应用架构**：所有样式、逻辑与标记均内聚在 `index.html` 中，无打包、无框架编译，加载仅毫秒级。
- **现代化布局**：基于 **CSS Grid** 与 CSS 动态变量（`--size`）实现自适应网格排版。
- **算法设计**：
  - **Fisher-Yates 随机洗牌算法**：保证地雷随机分布的均匀性与公平性。
  - **非递归栈模拟 Flood Fill**：避免大棋盘扩散时调用栈溢出（Stack Overflow）。
- **零外部请求**：脱机离线可用，无需加载任何外部 CDN 或字体资源。

---

## 🚀 本地运行与部署

### 1. 本地运行

无需安装任何运行环境（Node.js / Python 等），直接在文件管理器中双击打开：

```bash
# 或者通过命令行在本地浏览器预览
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

也可使用任意轻量 HTTP 静态服务器：

```bash
python3 -m http.server 8080
# 访问 http://localhost:8080
```

### 2. 静态托管部署

由于是纯静态单文件结构，可零成本部署在任意静态托管平台：

- **GitHub Pages**：将代码推送到 GitHub，在仓库 `Settings -> Pages` 选择 `main` 分支根目录即可。
- **Vercel / Netlify / Cloudflare Pages**：直接关联 GitHub 仓库，无需任何构建命令，自动部署发布。
- **Surge**：运行 `surge . your-custom-domain.surge.sh` 一键上线。

---

## 📄 开源协议

本项目基于 [MIT 许可证](LICENSE) 开放源代码，欢迎学习、分享与二次开发。
