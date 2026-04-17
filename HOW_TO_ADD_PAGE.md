# 如何加入新的作品页面 — VinK Portfolio 使用指南

---

## 网站文件结构

```
vink-portfolio/
├── index.html              ← 主页（保留原有设计）
├── film.html               ← Film 作品总览
├── xr.html                 ← XR & 3D 作品总览
├── about.html              ← 关于我页面
├── css/
│   └── style.css           ← 所有页面共用的样式
├── js/
│   └── main.js             ← 所有页面共用的脚本（cursor + reveal）
├── film/
│   ├── dreamer.html        ← Film 个别项目页（照这个格式新增）
│   └── ...
├── xr/
│   ├── bridgesxr.html      ← XR 个别项目页（照这个格式新增）
│   └── ...
└── images/
    ├── dreamer.jpg         ← 封面图（你自己放进去）
    ├── xr/
    │   └── guardian.jpg    ← XR 项目图
    └── ...
```

---

## 第一步：添加图片

把你的项目封面图放进 `images/` 文件夹：
- **Film 项目图** → 直接放 `images/` 内，例如 `images/dreamer.jpg`
- **XR 项目图** → 放 `images/xr/` 内，例如 `images/xr/guardian.jpg`

建议尺寸：**1920×1080px 或 16:9 比例**，压缩到 300KB 以内（可用 squoosh.app）。

---

## 第二步：新增 Film 作品页面

**复制任何一个现有的 film 页面**，例如 `film/dreamer.html`，重命名为你的新项目：

```
film/my-new-film.html
```

然后找这几个地方修改：

### 1. 页面标题（`<title>` 标签）
```html
<title>My New Film — Vincent Kong</title>
```

### 2. Hero 区域
```html
<!-- 修改这里的文字 -->
<p class="project-hero-eyebrow">Short Film · 2026 · Director · Editor</p>
<h1 class="project-hero-title">My New Film</h1>
<p class="project-hero-tagline">一句话介绍这个作品。</p>
<div class="project-award-badge">得奖信息（如果有的话）</div>

<!-- 修改背景图：把 images/my-new-film.jpg 换成你的图 -->
<div class="project-hero-bg" style="background: linear-gradient(135deg,#1a1205 50%,#2d1f08 100%);
  background-image: linear-gradient(to top,rgba(10,8,5,0.92) 0%,rgba(10,8,5,0.3) 60%,transparent 100%),
  url('../images/my-new-film.jpg'); background-size:cover; background-position:center;">
</div>
```

### 3. Meta 资料条
```html
<div class="meta-item"><div class="meta-label">Year</div><div class="meta-value">2026</div></div>
<div class="meta-item"><div class="meta-label">My Role</div><div class="meta-value">Director · Editor</div></div>
<div class="meta-item"><div class="meta-label">Team</div><div class="meta-value">Solo</div></div>
```

### 4. YouTube 嵌入（把 VIDEO_ID 换成你的 YouTube 影片 ID）
```html
<div class="project-embed">
  <iframe src="https://www.youtube.com/embed/VIDEO_ID" title="My New Film" allowfullscreen loading="lazy"></iframe>
</div>
```

YouTube 影片 ID 就是网址最后那段：
`https://youtu.be/`**`Z10iv_lunP0`** ← 这个就是 ID

### 5. Overview 文字
```html
<p>这里写你的项目介绍。</p>
<p>第二段，讲你的角色、挑战、成果。</p>
```

### 6. Prev / Next 导航（页面底部）
```html
<div class="project-nav">
  <a class="project-nav-link" href="dreamer.html">   <!-- 上一个项目 -->
    <p class="project-nav-dir">← Previous</p>
    <p class="project-nav-title">Dreamer</p>
    <p class="project-nav-tag">Short Film · LOKA 2nd Place</p>
  </a>
  <a class="project-nav-link next" href="../film.html">  <!-- 下一个 or 回到列表 -->
    <p class="project-nav-dir">Back to Film →</p>
    <p class="project-nav-title">All Film Works</p>
    <p class="project-nav-tag">Film Portfolio</p>
  </a>
</div>
```

---

## 第三步：把新页面加进总览

打开 `film.html`，在合适位置加入一个新的 card：

```html
<a class="card" href="film/my-new-film.html">
  <div class="card-bg" style="background: linear-gradient(135deg,#1a1205 50%,#2d1f08 100%);
    background-image: linear-gradient(to top,rgba(10,8,5,0.88) 0%,rgba(10,8,5,0.1) 40%,transparent 100%),
    url('images/my-new-film.jpg'); background-size:cover; background-position:center;">
  </div>
  <div class="card-overlay"></div>
  <div class="card-content">
    <p class="card-tag">Short Film · 2026 · Director</p>
    <h3 class="card-title">My New Film</h3>
    <p class="card-award">得奖信息（可选）</p>
    <p class="card-desc">一两句话描述这个作品。</p>
  </div>
  <span class="card-arrow">↗</span>
</a>
```

想要「宽版」card（占两格）：
```html
<a class="card wide" href="film/my-new-film.html">
```

---

## 新增 XR 作品页面

流程完全一样，只是：
- 复制 `xr/` 文件夹内的任何一个 HTML 文件
- 图片放 `images/xr/` 里
- CSS 路径已经是 `../css/style.css`（不用改）
- 在 `xr.html` 里加入对应的 card

---

## 上传到 GitHub Pages

1. 把整个 `vink-portfolio/` 文件夹的内容上传到你的 GitHub repo（`fangorr/vink-portfolio`）
2. 推送到 `main` 分支
3. GitHub Pages 会自动更新，通常 1-2 分钟生效

**注意：** 所有链接都是相对路径（`../css/style.css`），不需要改任何东西，直接上传就能用。

---

## 背景色参考（项目 Hero 用）

| 色调 | 适合用于 | CSS 值 |
|------|----------|--------|
| 暖棕 / 琥珀 | 暖调影片、Dreamer 类 | `linear-gradient(135deg,#1a1205 50%,#2d1f08 100%)` |
| 冷蓝绿 | 风景纪录片、Langit 类 | `linear-gradient(135deg,#080f10 50%,#0d1e1c 100%)` |
| 深红 | 戏剧、紧张感 | `linear-gradient(135deg,#100606 50%,#1a0a08 100%)` |
| 深紫蓝 | VR / 科技感 | `linear-gradient(135deg,#0a0a1a 50%,#101030 100%)` |
| 深紫 | 神秘 / 艺术 | `linear-gradient(135deg,#080510 50%,#100a18 100%)` |
| 深绿 | 自然 / AR 类 | `linear-gradient(135deg,#0a1008 50%,#101808 100%)` |

---

如有疑问，把具体问题发给 Claude，它会帮你解决！
