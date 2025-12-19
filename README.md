# 🌍 我们的爱情足迹 (Love Footprint 3D)

> 一个基于 WebGL 的 3D 地球纪念网站，记录我们一起走过的每一个角落。
> A romantic 3D interactive globe to record our memories and travel footprints.

<p align="center">
  <img src="screenshot.gif" alt="Project Demo" width="100%">
</p>

## ✨ 项目简介 (Introduction)

这是一个纯静态的网页项目，利用 [Globe.gl](https://github.com/vasturiano/globe.gl) 渲染出一个可交互的 3D 地球。

你可以用它来标记情侣之间的纪念地、旅行足迹或是异地恋的距离。用户点击地球上的标记卡片时，镜头会平滑地飞向该地点（下探）；点击地球空白处，镜头会自动拉远并恢复自转。**如果有视频，屏幕会自动播放一段沉浸式的回忆短片**。

**核心特点：**

- 🌏 **真·3D 交互**：支持拖拽、缩放、360度旋转。
- 🎬 **沉浸视频**：支持点击卡片自动播放 MP4 纪念视频，让回忆动起来（新功能！）。
- 🚀 **丝滑动画**：点击卡片自动“飞行”定位，体验如电影转场般流畅。
- 🖼️ **图文展示**：支持自定义每个地点的照片、名称和描述。
- ⚡ **零成本部署**：纯静态 HTML/JS，无需后端服务器，完美适配 Cloudflare Pages / GitHub Pages。
- 🔒 **交互优化**：内置防误触机制，解决了“下探后无法恢复”的常见交互冲突。

## 🎮 在线演示 (Demo)

点击查看演示效果：[你的演示链接 (例如: https://20130506.xyz)]

## 🛠️ 快速开始 (Quick Start)

本项目不需要复杂的构建工具（如 Webpack/Vite），**开箱即用**。

### 1. 下载或 Fork 项目
你可以直接点击右上角的 **Fork** 按钮，将项目复制到你的 GitHub 仓库；或者直接下载 ZIP 包。

### 2. 修改内容
打开项目根目录下的 `index.html` 文件，找到 `myPlaces` 数组配置区：

```javascript
// 在 index.html 的 script 标签内
// 在 index.html 的 script 标签内
const myPlaces = [
  { 
    lat: 39.9042,     // 纬度 (可通过 Google Maps/高德地图获取)
    lng: 116.4074,    // 经度
    name: "北京 · 相识",           // 地点名称
    img: "[https://example.com/photo1.jpg](https://example.com/photo1.jpg)", // 卡片封面图
    desc: "2021.05.20<br>故事开始的地方",    // 描述文字
    video: "[https://example.com/memories.mp4](https://example.com/memories.mp4)" // [可选] 视频链接，留空 "" 则只下探不播放
  },
  // 复制上面的 { ... }, 添加更多地点
  {
    lat: 48.8566, 
    lng: 2.3522, 
    name: "巴黎 · 未来",
    img: "[https://example.com/photo2.jpg](https://example.com/photo2.jpg)",
    desc: "下一站目的地",
    video: "" // 没有视频时，留空即可
  }
];
```

### 💡 关于视频链接的重要提示

为了保证视频能稳定播放，建议使用 **直链 (Direct Link)**：

- ✅ **推荐方案**：将视频上传到 **Cloudflare R2**、阿里云 OSS 或自己的服务器，获取 `.mp4` 结尾的链接。
- ✅ **替代方案**：使用 Internet Archive 等公共库的直链。
- ❌ **不推荐**：直接使用 YouTube/Bilibili 的网页链接（因为存在跨域限制，无法直接嵌入播放）。

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

## 📄 开源协议 (License)

MIT License. 你可以随意修改、使用和分发此代码。祝你们幸福！❤️