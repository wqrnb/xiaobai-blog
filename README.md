# 小白超白的 · 星球庄园 3D 博客

「小白超白的」个人作品集融合站：B 的球面轨道巡游 + A 的真实作品贴图 + 博客式内容面板。

线上目标：`https://wqrnb.github.io/xiaobai-blog/`

## 特性

- **3D 星球庄园**：B 的程序化粉色星球（发光经纬网格、能量河流、云层、星环、水晶），球面轨道相机，拖拽惯性，松手自动吸附五个分区。
- **真实作品画框**：A 的 74 件作品贴图以 JS data-URI 脚本悬浮在星球表面，点击画框或搜索可打开文章式详情。
- **五分区全息面板**：关于小白 / 精选 / 小红书岛 / B站视频墙 / 关注，连接光束 + 3D 翻转 + 玻璃拟态。
- **完整交互**：`/` 或 Ctrl+K 搜索（传送 + 高亮）、`B` 脉冲、日夜切换（记住偏好）、A 的 CC0 WAV 音乐、鼠标光点/星尘、卡片 3D 倾斜。
- **兼容**：纯静态，`file://` 直接打开 / `?view=2d` 轻量模式 / 移动端底部面板 / 无 CDN、无构建、无网络依赖。

## 目录

```text
site root
├─ index.html
├─ assets/
│  ├─ css/style.css
│  ├─ js/data.js          # 合并数据：A 的 74 件单源 + B 的 meta/stats
│  ├─ js/three-bg.js      # B 轨道相机 + A 画框
│  ├─ js/app.js           # 面板/搜索/详情/音乐
│  ├─ textures/           # A 的 JS data-URI 贴图
│  ├─ images/             # A 的 webp 封面 + B 的备选封面
│  ├─ audio/starlit-steps.wav
│  └─ lib/                # Three.js r128 本地库（保留 B 的已验证管线）
```

## 运行

直接双击 `index.html`，或启动任意静态服务器。

## 部署

```powershell
cd E:\360MoveData\Users\25348\Desktop\xiaobai-blog
git add .
git commit -m "update: xiaobai-blog"
gh repo create xiaobai-blog --public --source=. --remote=origin --push
gh api repos/wqrnb/xiaobai-blog/pages -X POST -f "source[branch]=main" -f "source[path]=/"
```

如果仓库已存在：

```powershell
git remote add origin https://github.com/wqrnb/xiaobai-blog.git
git push -u origin main
gh api repos/wqrnb/xiaobai-blog/pages -X POST -f "source[branch]=main" -f "source[path]=/"
```

## 素材与许可

- 作品封面、标题、数据来自「小白超白的」公开主页，仅用于个人作品集展示。
- 背景音乐 `assets/audio/starlit-steps.wav` 为原创 CC0，许可见 `assets/audio/LICENSE-CC0.md`。
- 3D 库见 `assets/lib/THREE-LICENSE.txt`。