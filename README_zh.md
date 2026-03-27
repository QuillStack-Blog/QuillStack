<img src="https://socialify.git.ci/QuillStack-Blog/QuillStack/image?custom_language=Next.js&description=1&font=Source+Code+Pro&forks=1&issues=1&language=1&logo=https%3A%2F%2Frepository-images.githubusercontent.com%2F1170537249%2Fef56bd08-6f8f-4112-a075-ebb06c73566b&name=1&owner=1&pattern=Floating+Cogs&pulls=1&stargazers=1&theme=Auto" alt="QuillStack" width="640" height="320" />

👋👋🏻👋🏼👋🏽👋🏾👋🏿

**中文** | [English](https://github.com/QuillStack-Blog/QuillStack/blob/main/README.md)

你好，欢迎来到 QuillStack！这是一个由 SnowBall (@SnowBall-Bqiu) 发起的 NextJS 项目。

[提交历史](https://github.com/QuillStack-Blog/QuillStack/commits/main)

> 特别说明：编译之后（out目录下）以及您编写的博文（content目录下）的所有文件的所有权归您所有，您可以将其代码可见性随意设置为私有。使用此项目请务必保留页脚的项目地址以及名称。

> Special Note: All files in the out directory after compilation, as well as the blog posts you wrote in the content directory, are owned by you. You can freely set their code visibility to private. When using this project, be sure to retain the project address and name in the footer.
---

## 🛠️ 技术栈

| 技术 | 描述 |
|------|------|
| [Next.js 15](https://nextjs.org) | React 框架，支持 App Router |
| [Tailwind CSS](https://tailwindcss.com) | 实用优先的 CSS 框架 |
| [TypeScript](https://www.typescriptlang.org) | 类型安全的 JavaScript |
| [shadcn/ui](https://ui.shadcn.com) | 精美的 UI 组件（基于 Radix UI） |
| [@vercel/og](https://vercel.com/og) | Open Graph 图片生成 |
| [marked](https://marked.js.org) | Markdown 解析器 |
| [date-fns](https://date-fns.org) | 日期工具库 |

---

## ✨ 功能特性

- 📱 **响应式设计** - 移动端优先，适配所有设备
- 🌙 **暗色/亮色主题** - 基于 `next-themes` 的自动主题切换
- 🔍 **SEO 优化** - JSON-LD、Open Graph、Twitter Cards
- 🖼️ **自动 OG 图片** - 自动生成社交分享卡片
- 📚 **文章目录** - 自动提取 Markdown 标题生成文章侧边目录
- ⬆️ **返回顶部按钮** - 支持配置显示阈值的悬浮返回顶部按钮
- 🧭 **嵌套导航菜单** - 顶部导航支持分组下拉菜单
-  **友链系统** - 带申请系统的友链页面
- 📄 **Markdown 支持** - 完整 Markdown 语法，支持代码高亮
- 📑 **分类系统** - 按分类组织文章
- 📊 **分页功能** - 可配置的每页文章数

---

## 快速开始

```bash
# 安装依赖
npm install

# 开发模式
npm run dev

# 构建生产版本
npm run build

# 启动生产服务器
npm run start
```

---

## 配置指南

### 站点配置 (`content/settings.json`)

站点的主配置文件，包含以下部分：

#### 基本信息

| 字段 | 描述 | 示例 |
| ----------------- | ------------------- | --------------------------------- |
| `siteTitle` | 网站标题 | `"我的博客"` |
| `siteDescription` | 网站描述（用于 SEO） | `"这是一个个人博客..."` |

#### 头部信息 (`header`)

| 字段 | 描述 | 示例 |
| -------------- | ------------ | ---------------------------------- |
| `title` | 博主姓名 | `"你的名字"` |
| `bio` | 个人简介 | `"我是一名软件工程师..."` |
| `avatarUrl` | 头像 URL | `"https://example.com/avatar.jpg"` |
| `avatarHint` | 头像 alt / 图片提示文本 | `"作者头像"` |
| `heroImageUrl` | 首页横幅图片 | `"https://example.com/hero.jpg"` |
| `heroImageHint` | 横幅 alt / 图片提示文本 | `"编程工作台"` |

#### 作者信息 (`author`)

| 字段 | 描述 |
| ----------- | -------- |
| `name` | 作者姓名 |
| `avatarUrl` | 作者头像 |
| `avatarHint` | 作者头像 alt / 图片提示文本 |

#### 分页设置 (`pagination`)

| 字段 | 描述 | 默认值 |
| -------------- | -------------- | ------ |
| `postsPerPage` | 每页文章数 | `10` |

#### 返回顶部设置 (`backToTop`)

| 字段 | 描述 | 默认值 |
| -------------- | -------------- | ------ |
| `showAfter` | 页面滚动多少像素后显示悬浮返回顶部按钮 | `400` |

#### 导航菜单 (`navigation`)

```json
"navigation": [
  { "id": "1", "label": "首页", "href": "/" },
  {
    "id": "2",
    "label": "资源",
    "items": [
      { "id": "2-1", "label": "全部分类", "href": "/category" },
      { "id": "2-2", "label": "友链", "href": "/friends" }
    ]
  }
]
```

| 字段 | 描述 |
| ------- | ------------------------ |
| `id` | 导航项唯一标识 |
| `label` | 导航显示文本 |
| `href` | 直达链接项的目标地址 |
| `items` | 分组菜单下的子导航项数组 |

> ⚠️ 每个导航项必须至少提供 `href` 或 `items` 其中之一。

#### 分类配置 (`categories`)

```json
"categories": [
  { "id": "tech", "name": "技术", "color": "#3b82f6" },
  { "id": "server", "name": "服务器", "color": "#8b5cf6" },
  { "id": "thoughts", "name": "随笔", "color": "#f97316" }
]
```

| 字段 | 描述 |
| ------- | ------------------------ |
| `id` | 分类标识符（用于文章关联） |
| `name` | 分类显示名称 |
| `color` | 分类颜色（十六进制） |

#### 底部配置 (`footer`)

```json
"footer": {
  "text": "© 2025 我的博客。保留所有权利。",
  "brandName": "我的博客",
  "brandDescription": "一个基于 Next.js 的轻量博客。",
  "logoIcon": "https://example.com/logo.svg",
  "madeIn": "Open Source",
  "socialLinks": [
    { "id": "social-1", "label": "GitHub", "href": "https://github.com/example" }
  ],
  "linkSections": [
    {
      "id": "section-1",
      "title": "资源",
      "links": [
        { "id": "link-1-1", "label": "文档", "href": "https://nextjs.org/docs" }
      ]
    }
  ],
  "legalLinks": [
    { "id": "legal-1", "label": "AGPL-3.0", "href": "https://www.gnu.org/licenses/agpl-3.0.html" }
  ]
}
```

| 字段 | 描述 |
| ------- | ------------------------ |
| `text` | 页脚版权文本 |
| `brandName` | 页脚品牌名称 |
| `brandDescription` | 页脚品牌简介 |
| `logoIcon` | 可选品牌图标 / Logo 地址 |
| `madeIn` | 附加页脚徽标文本 |
| `socialLinks` | 社交媒体 / 社区链接 |
| `linkSections` | 分组页脚链接区块 |
| `legalLinks` | 法务 / 许可证链接 |

#### 主题配置 (`theme`)

| 字段 | 描述 | 示例 |
| -------------- | -------- | ----------------- |
| `bodyFont` | 正文字体 | `"PT Sans"` |
| `headlineFont` | 标题字体 | `"Space Grotesk"` |

#### SEO 配置 (`seo`)

| 字段 | 描述 |
| --------------- | -------------- |
| `siteUrl` | 用于 canonical 与站点元数据的正式站点域名 |
| `ogImageGenerationLimit` | 构建时使用本地生成 OG 图的文章数量上限 |
| `fallbackOgImage` | 本地生成图或封面不可用时的兜底分享图地址 |
| `keywords` | SEO 关键词数组 |
| `twitterHandle` | Twitter 账号 |

#### OG 图片配置 (`ogImage`)

生成社交媒体分享卡片的样式配置。

---

## 文章管理教程

### 文章结构

博客文章由两部分组成：

1. **文章元数据**：`content/sitedoc.json` 中的 `articles` 数组
2. **文章内容**：`content/doc/` 目录下的 `.md` 文件

### 添加新文章

#### 第 1 步：创建 Markdown 文件

在 `content/doc/` 目录下创建一个新的 `.md` 文件，例如 `10.md`：

```markdown
## 我的第一篇文章

这里是文章内容，支持完整的 Markdown 语法。

### 小标题

- 列表项 1
- 列表项 2

**粗体**和*斜体*文本。

\`\`\`javascript
// 代码块
console.log("Hello World");
\`\`\`
```

如果你的代码真的~~很长，渲染后的文章代码块会自动显示一个小的水平滚动条，允许你左右滑动查看完整代码，像这样：

```markdown
这是一个超级超级长的代码块\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/
```

#### 第 2 步：注册文章元数据

添加到 `content/sitedoc.json` 中的 `articles` 数组：

```json
{
  "id": "10",
  "slug": "my-first-post",
  "title": "我的第一篇文章",
  "contentPath": "content/doc/10.md",
  "publishedAt": "2024-08-10T12:00:00.000Z",
  "excerpt": "这是文章摘要，显示在文章列表中。",
  "imageUrl": "https://images.unsplash.com/photo-xxx",
  "imageHint": "图片描述",
  "categoryId": "tech"
}
```

#### 字段说明

| 字段 | 必填 | 描述 |
| ------------- | ---- | -------------------------------------- |
| `id` | ✅ | 文章唯一标识符（字符串） |
| `slug` | ✅ | URL 路径标识符，例如 `my-first-post` |
| `title` | ✅ | 文章标题 |
| `contentPath` | ✅ | Markdown 文件路径 |
| `publishedAt` | ✅ | 发布时间（ISO 8601 格式） |
| `excerpt` | ✅ | 文章摘要（显示在列表页面） |
| `imageUrl` | ✅ | 封面图片 URL |
| `imageHint` | ⬜ | 图片描述（用于无障碍） |
| `categoryId` | ✅ | 分类 ID，对应 `settings.json` 中的分类 |

> ⚠️ 注意：如果上面的可空字段导致构建错误，可以保持配置项但值为空。

### 文章排序

文章按 `publishedAt` 时间降序排列，最新的文章显示在最前面。

### 删除文章

1. 从 `sitedoc.json` 的 `articles` 数组中移除对应的条目
2. （可选）删除对应的 `.md` 文件

### 修改文章

1. 直接编辑对应的 `.md` 文件来修改内容
2. 如需修改标题、摘要等，编辑 `sitedoc.json` 中对应的条目

---

## 友链

项目包含一个友链系统，配置在 `content/friends.json` 中。

### 配置

```json
{
  "description": "友链描述",
  "applyInfo": {
    "title": "申请友链",
    "description": "如何申请...",
    "email": "your@email.com",
    "agreement": "协议文本"
  },
  "links": [
    {
      "id": "friend-id",
      "name": "友链名称",
      "description": "友链描述",
      "avatar": "https://example.com/avatar.png",
      "url": "https://example.com",
      "tags": ["标签1", "标签2"]
    }
  ]
}
```

### 添加友链

1. 编辑 [`content/friends.json`](content/friends.json)
2. 在 `links` 数组中添加一个新的对象
3. 保存文件 - 友链页面会自动更新

---

## OG 图片生成

项目在构建过程中会自动生成用于社交媒体分享的 Open Graph 图片。你也可以手动生成：

```bash
# 生成 OG 图片
npm run build:og
```

### 配置

OG 图片设置在 [`content/settings.json`](content/settings.json) 的 `ogImage` 部分：

```json
{
  "ogImage": {
    "slogan": "你的标语",
    "primaryColor": "#3b82f6",
    "backgroundColor": "#0f172a",
    "gradientEndColor": "#1e293b",
    "textColor": "#f8fafc",
    "secondaryTextColor": "#94a3b8",
    "tertiaryTextColor": "#64748b"
  }
}
```

---

## 部署

### Vercel（推荐）

1. Fork GitHub 仓库
2. 前往 [Vercel](https://vercel.com) 导入仓库
3. Vercel 会自动检测 Next.js 并配置构建设置
4. 点击部署

### Netlify

1. Fork GitHub 仓库
2. 前往 [Netlify](https://netlify.com) 导入仓库
3. 构建命令：`npm run build`
4. 发布目录：`out`
5. 点击部署

---

## 注意事项

1. 修改配置后重启开发服务器
2. `categoryId` 必须与 `settings.json` 中的分类 `id` 匹配
3. 图片建议使用 CDN 链接，避免在仓库中放置大图片
4. 发布时间格式：`YYYY-MM-DDTHH:mm:ss.sssZ`
5. 开发服务器运行在 9002 端口：`npm run dev`

---

## 许可证

[AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.html) - 详见 [LICENSE](LICENSE) 文件。

> **注意**：本项目采用 AGPL-3.0 许可证。如果您使用本项目提供网络服务，必须在相同许可证下开源您的修改。

---

## 请我喝杯咖啡

| 微信 | <img src="https://github.com/user-attachments/assets/29c0f96f-4d85-4f99-9dee-23cde279fdd1" alt="mm_reward_qrcode_1772603144418" style="zoom: 33%;" /> |
| -------------- | ------------------------------------------------------------ |
