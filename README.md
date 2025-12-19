# 🌍 我们的爱情足迹 (Love Footprint 3D)

> 一个基于 WebGL 的 3D 地球纪念网站，记录我们一起走过的每一个角落。
> A romantic 3D interactive globe to record our memories and travel footprints.

<p align="center">
  <img src="screenshot.gif" alt="Project Demo" width="100%">
</p>

## ✨ 项目简介 (Introduction)

这是一个纯静态的网页项目，利用 [Globe.gl](https://github.com/vasturiano/globe.gl) 渲染出一个可交互的 3D 地球。

你可以用它来标记情侣之间的纪念地、旅行足迹或是异地恋的距离。用户点击地球上的标记卡片时，镜头会平滑地飞向该地点（下探）；点击地球空白处，镜头会自动拉远并恢复自转。

**核心特点：**
- 🌏 **真·3D 交互**：支持拖拽、缩放、360度旋转。
- 🚀 **丝滑动画**：点击卡片自动“飞行”定位，体验如电影转场般流畅。
- 🖼️ **图文展示**：支持自定义每个地点的照片、名称和描述。
- ⚡ **零成本部署**：纯静态 HTML/JS，无需后端服务器，完美适配 Cloudflare Pages / GitHub Pages。
- 🔒 **交互优化**：内置防误触机制，解决了“下探后无法恢复”的常见交互冲突。

## 🎮 在线演示 (Demo)

点击查看演示效果：[你的演示链接 (例如: https://love.yourdomain.com)]

*(如果没有演示链接，可以删掉这一行)*

## 🛠️ 快速开始 (Quick Start)

本项目不需要复杂的构建工具（如 Webpack/Vite），**开箱即用**。

### 1. 下载或 Fork 项目
你可以直接点击右上角的 **Fork** 按钮，将项目复制到你的 GitHub 仓库；或者直接下载 ZIP 包。

### 2. 修改内容
打开项目根目录下的 `index.html` 文件，找到 `myPlaces` 数组配置区：

```javascript
// 在 index.html 的 script 标签内
const myPlaces = [
  { 
    lat: 39.9042,     // 纬度 (可通过 Google Maps/高德地图获取)
    lng: 116.4074,    // 经度
    name: "北京 · 相识",           // 地点名称
    img: "[https://example.com/photo1.jpg](https://example.com/photo1.jpg)", // 照片链接 (推荐使用图床或 R2)
    desc: "2021.05.20<br>故事开始的地方"     // 描述文字 (支持 <br> 换行)
  },
  // 复制上面的 { ... }, 添加更多地点
  {
    lat: 48.8566, 
    lng: 2.3522, 
    name: "巴黎 · 未来",
    img: "[https://example.com/photo2.jpg](https://example.com/photo2.jpg)",
    desc: "下一站目的地"
  }
];
```

### 3. 本地预览

直接双击打开 `index.html` 可能会因为浏览器安全策略导致图片无法加载。 **推荐方式：** 使用 VS Code 安装 `Live Server` 插件，右键 `index.html` -> `Open with Live Server`。

## 🚀 部署指南 (Deployment)

推荐使用 **Cloudflare Pages** 进行免费、高速的全球部署。

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)。
2. 进入 **Workers & Pages** -> **Create Application** -> **Pages** -> **Connect to Git**。
3. 选择你 Fork 的 GitHub 仓库 (`love-footprint` 或你起的名字)。
4. **Build settings (构建配置)**：
   - Framework preset: `None` (空)
   - Build command: (留空)
   - Build output directory: (留空，或者填 `/`)
5. 点击 **Save and Deploy**。

几秒钟后，Cloudflare 会分配给你一个 `xxx.pages.dev` 的域名，你的纪念网站就上线了！

## ⚙️ 高级配置 (Advanced)

如果你懂一点前端代码，可以尝试修改以下参数：

- **更换地球贴图**： 搜索 `.globeImageUrl(...)`，可以换成更高清的地球图片或复古风格地图。
- **调整自转速度**： 修改 `world.controls().autoRotateSpeed = 0.6;` (数值越大转得越快)。
- **调整飞行高度**： 修改 `altitude: 0.3` (数值越小，下探时离地面越近)。

## 🤝 贡献与致谢 (Credits)

- 核心库：[Globe.gl](https://github.com/vasturiano/globe.gl) by vasturiano
- 灵感来源：[GitHub Open Source Community]

## 📄 开源协议 (License)

MIT License. 你可以随意修改、使用和分发此代码。祝你们幸福！❤️