# 💻 Tech Resume

一个现代化、响应式且带有动态可视化后台的科技风个人简历网站。

基于 **React + TypeScript + Vite + Tailwind CSS** 构建，后端采用轻量级的 **Node.js (Express) + SQLite**。它不仅可以作为静态的在线简历，还支持通过后台面板实时动态修改展示内容，包括但不限于你的基本信息、技能矩阵、经历时间线、项目精选以及页面的模块开关等。

---

## ✨ 核心特性

- 🎨 **现代化 UI 设计**：科技感暗黑主题，卡片悬浮、毛玻璃效果，响应式适配移动端。
- ⚡ **轻量级全栈**：前后端分离。前端 React + Vite 极致加载；后端 Node + SQLite 即插即用，无需配置复杂的数据库。
- 🛠️ **所见即所得后台管理**：
  - **动态修改内容**：实时编辑基本信息、头像、技能条、工作/教育经历与项目展示。
  - **本地图片上传**：内置基于 `multer` 的本地图床，方便一键替换头像与 Favicon。
  - **模块展示开关**：通过控制面板自由切换是否展示特定的简历模块。
  - **安全登录与改密**：JWT 认证保护，可随时重置或修改管理员账号密码。
- 🔄 **一键还原模板**：支持一键清空数据，恢复为开源默认的测试数据模板。

## 🚀 快速开始

### 环境要求

- Node.js >= 18.x
- npm 或 yarn

### 1. 克隆项目并安装依赖

```bash
git clone https://github.com/your-username/JLwz.git
cd JLwz/resume-site
npm install
```

### 2. 本地开发运行

本项目使用 `concurrently` 实现一键同时启动前端 Vite 开发服务器和后端 Express API 服务。

```bash
npm run dev
```

- 前台简历页面：[http://localhost:5173](http://localhost:5173)
- 后台管理面板：[http://localhost:5173/admin](http://localhost:5173/admin)
  - **默认管理员账号**：`admin`
  - **默认管理员密码**：`admin123`

> ⚠️ **安全提示**：第一次登录后台后，请务必前往「账号设置」修改默认密码！

### 3. 构建与部署

构建生产环境所需的静态文件：

```bash
npm run build
```

构建产物将输出到 `dist` 目录。

后端服务生产部署（可选，可根据你的环境编写守护脚本如 PM2 / Docker）：

```bash
# 执行编译后的 JS 或直接通过 tsx 运行
npx tsx api/server.ts
```

*提示：部署时，请确保 `public/uploads` 目录的读写权限，以及 `database.sqlite` 所在目录的写权限。同时，建议通过环境变量覆盖后端的 `JWT_SECRET` 以保障认证安全。*

## 📁 目录结构

```
├── api/                  # Node.js 后端服务
│   ├── server.ts         # Express 服务器入口
│   ├── db.ts             # SQLite 数据库配置
│   └── init.ts           # 数据库建表与初始数据脚本
├── src/                  # React 前端代码
│   ├── components/       # UI 通用组件与页面区块
│   ├── data/             # 简历默认测试模板数据
│   ├── pages/            # 路由页面（Home / Admin Dashboard）
│   └── store/            # Zustand 状态管理
├── public/               # 静态资源与上传目录
└── vite.config.ts        # Vite 配置（包含前端代理 API 设置）
```

## 📄 免责声明

本项目及源代码仅供**个人学习、技术研究与交流**使用。

使用者在本项目基础上进行的任何二次开发、修改、部署、商业行为或恶意行为（包括但不限于用于非法用途或造成数据泄露等）均与本项目原作者无关。**相关责任和法律后果由使用者自行承担。**

---

## 📜 开源协议

本项目采用 [MIT License](LICENSE) 协议开源。你可以自由地使用、修改和分发，但请务必遵守上述免责声明并保留原作者的版权声明。欢迎在 GitHub 上提交 Issue 与 PR 参与共建！
