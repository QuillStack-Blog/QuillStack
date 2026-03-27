
<img src="https://socialify.git.ci/QuillStack-Blog/QuillStack/image?custom_language=Next.js&description=1&font=Source+Code+Pro&forks=1&issues=1&language=1&logo=https%3A%2F%2Frepository-images.githubusercontent.com%2F1170537249%2Fef56bd08-6f8f-4112-a075-ebb06c73566b&name=1&owner=1&pattern=Floating+Cogs&pulls=1&stargazers=1&theme=Auto" alt="QuillStack" width="2740" height="420" />

👋👋🏻👋🏼👋🏽👋🏾👋🏿

**English** | [中文](README_zh.md)

Hello, welcome to QuillStack! This is a NextJS project initiated by SnowBall (@SnowBall-Bqiu).

[Commit History](https://github.com/QuillStack-Blog/QuillStack/commits/main)

> 特别说明：编译之后（out目录下）以及您编写的博文（content目录下）的所有文件的所有权归您所有，您可以将其代码可见性随意设置为私有。使用此项目请务必保留页脚的项目地址以及名称。

> Special Note: All files in the out directory after compilation, as well as the blog posts you wrote in the content directory, are owned by you. You can freely set their code visibility to private. When using this project, be sure to retain the project address and name in the footer.

---

## 🛠️ Tech Stack

| Technology | Description |
|------------|-------------|
| [Next.js 15](https://nextjs.org) | React framework with App Router |
| [Tailwind CSS](https://tailwindcss.com) | Utility-first CSS framework |
| [TypeScript](https://www.typescriptlang.org) | Type-safe JavaScript |
| [shadcn/ui](https://ui.shadcn.com) | Beautiful UI components (based on Radix UI) |
| [@vercel/og](https://vercel.com/og) | Open Graph image generation |
| [marked](https://marked.js.org) | Markdown parser |
| [date-fns](https://date-fns.org) | Date utility library |

---

## ✨ Features

- 📱 **Responsive Design** - Mobile-first, works on all devices
- 🌙 **Dark/Light Theme** - Automatic theme switching with `next-themes`
- 🔍 **SEO Optimized** - JSON-LD, Open Graph, Twitter Cards
- 🖼️ **Auto OG Images** - Automatically generated social sharing cards
- 📚 **Table of Contents** - Automatically extracts Markdown headings into an article sidebar
- ⬆️ **Back to Top Button** - Floating scroll-to-top button with configurable display threshold
- 🧭 **Nested Navigation** - Header navigation supports grouped menu items
- 🔗 **Friends Links** - Friends page with application system
- 📄 **Markdown Support** - Full Markdown syntax with code highlighting
- 📑 **Category System** - Organize articles by categories
- 📊 **Pagination** - Configurable posts per page

---

## Quick Start

```bash
# Install dependencies
npm install

# Development mode
npm run dev

# Build production version
npm run build

# Start production server
npm run start
```

---

## Configuration Guide

### Site Configuration (`content/settings.json`)

The main configuration file for the site, containing the following sections:

#### Basic Information

| Field | Description | Example |
| ----------------- | ------------------- | --------------------------------- |
| `siteTitle` | Website Title | `"My Blog"` |
| `siteDescription` | Website Description (for SEO) | `"My Blog is a personal blog..."` |

#### Header Information (`header`)

| Field | Description | Example |
| -------------- | ------------ | ---------------------------------- |
| `title` | Blogger Name | `"Your Name"` |
| `bio` | Personal Bio | `"I'm a software engineer..."` |
| `avatarUrl` | Avatar URL | `"https://example.com/avatar.jpg"` |
| `avatarHint` | Avatar alt / image hint text | `"Portrait of the author"` |
| `heroImageUrl` | Homepage banner image | `"https://example.com/hero.jpg"` |
| `heroImageHint` | Banner alt / image hint text | `"Coding workspace"` |

#### Author Information (`author`)

| Field | Description |
| ----------- | -------- |
| `name` | Author Name |
| `avatarUrl` | Author Avatar |
| `avatarHint` | Author avatar alt / image hint text |

#### Pagination Settings (`pagination`)

| Field | Description | Default Value |
| -------------- | -------------- | ------ |
| `postsPerPage` | Number of posts per page | `10` |

#### Back to Top Settings (`backToTop`)

| Field | Description | Default Value |
| -------------- | -------------- | ------ |
| `showAfter` | Scroll distance in pixels before the floating back-to-top button appears | `400` |

#### Navigation Menu (`navigation`)

```json
"navigation": [
  { "id": "1", "label": "Home", "href": "/" },
  {
    "id": "2",
    "label": "Resources",
    "items": [
      { "id": "2-1", "label": "All Categories", "href": "/category" },
      { "id": "2-2", "label": "Friends", "href": "/friends" }
    ]
  }
]
```

| Field | Description |
| ------- | ------------------------ |
| `id` | Navigation item identifier |
| `label` | Display text |
| `href` | Link target for a direct navigation item |
| `items` | Nested child navigation items for grouped menus |

> ⚠️ Each navigation item must provide either `href` or `items`.

#### Category Configuration (`categories`)

```json
"categories": [
  { "id": "tech", "name": "Technology", "color": "#3b82f6" },
  { "id": "server", "name": "Server", "color": "#8b5cf6" },
  { "id": "thoughts", "name": "Essays", "color": "#f97316" }
]
```

| Field | Description |
| ------- | ------------------------ |
| `id` | Category identifier (for article association) |
| `name` | Category display name |
| `color` | Category color (hexadecimal) |

#### Footer Configuration (`footer`)

```json
"footer": {
  "text": "© 2025 My Blog. All rights reserved.",
  "brandName": "My Blog",
  "brandDescription": "A lightweight blog built with Next.js.",
  "logoIcon": "https://example.com/logo.svg",
  "madeIn": "Open Source",
  "socialLinks": [
    { "id": "social-1", "label": "GitHub", "href": "https://github.com/example" }
  ],
  "linkSections": [
    {
      "id": "section-1",
      "title": "Resources",
      "links": [
        { "id": "link-1-1", "label": "Docs", "href": "https://nextjs.org/docs" }
      ]
    }
  ],
  "legalLinks": [
    { "id": "legal-1", "label": "AGPL-3.0", "href": "https://www.gnu.org/licenses/agpl-3.0.html" }
  ]
}
```

| Field | Description |
| ------- | ------------------------ |
| `text` | Footer copyright text |
| `brandName` | Footer brand name |
| `brandDescription` | Short footer brand description |
| `logoIcon` | Optional brand icon / logo URL |
| `madeIn` | Additional footer badge text |
| `socialLinks` | Social media / community links |
| `linkSections` | Grouped footer link sections |
| `legalLinks` | Legal / license links |

#### Theme Configuration (`theme`)

| Field | Description | Example |
| -------------- | -------- | ----------------- |
| `bodyFont` | Body font | `"PT Sans"` |
| `headlineFont` | Headline font | `"Space Grotesk"` |

#### SEO Configuration (`seo`)

| Field | Description |
| --------------- | -------------- |
| `siteUrl` | Official website domain used for canonical URLs and metadata |
| `ogImageGenerationLimit` | Number of articles that use generated local OG images during build |
| `fallbackOgImage` | Fallback share image URL when generated/local cover is unavailable |
| `keywords` | SEO keywords array |
| `twitterHandle` | Twitter handle |

#### OG Image Configuration (`ogImage`)

Style configuration for generating social media sharing cards.

---

## Article Management Tutorial

### Article Structure

Blog articles consist of two parts:

1. **Article Metadata**: `articles` array in `content/sitedoc.json`
2. **Article Content**: `.md` files in `content/doc/` directory

### Adding a New Article

#### Step 1: Create Markdown File

Create a new `.md` file in `content/doc/` directory, e.g., `10.md`:

```markdown
## My First Article

Here is the article content, supporting full Markdown syntax.

### Subheading

- List item 1
- List item 2

**Bold** and *italic* text.

\`\`\`javascript
// Code block
console.log("Hello World");
\`\`\`
```

If your code is really~~long, the rendered article's code block will automatically show a small horizontal scrollbar, allowing you to swipe left and right to view the complete code, like this:

```markdown
This is a super duper long code block\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/\O/
```

#### Step 2: Register Article Metadata

Add to the `articles` array in `content/sitedoc.json`:

```json
{
  "id": "10",
  "slug": "my-first-post",
  "title": "My First Article",
  "contentPath": "content/doc/10.md",
  "publishedAt": "2024-08-10T12:00:00.000Z",
  "excerpt": "This is the article summary, displayed in the article list.",
  "imageUrl": "https://images.unsplash.com/photo-xxx",
  "imageHint": "Description of image content",
  "categoryId": "tech"
}
```

#### Field Descriptions

| Field | Required | Description |
| ------------- | ---- | -------------------------------------- |
| `id` | ✅ | Article unique identifier (string) |
| `slug` | ✅ | URL path identifier, e.g., `my-first-post` |
| `title` | ✅ | Article title |
| `contentPath` | ✅ | Markdown file path |
| `publishedAt` | ✅ | Publication time (ISO 8601 format) |
| `excerpt` | ✅ | Article summary (displayed in list page) |
| `imageUrl` | ✅ | Cover image URL |
| `imageHint` | ⬜ | Image description (for accessibility) |
| `categoryId` | ✅ | Category ID, corresponding to categories in `settings.json` |

> ⚠️ Note: If the nullable fields above cause build errors, you can keep the configuration item with an empty value.

### Article Sorting

Articles are sorted in descending order by `publishedAt` time, with the newest articles displayed first.

### Deleting Articles

1. Remove the corresponding entry from the `articles` array in `sitedoc.json`
2. (Optional) Delete the corresponding `.md` file

### Modifying Articles

1. Directly edit the corresponding `.md` file to modify content
2. To modify title, summary, etc., edit the corresponding entry in `sitedoc.json`

---

## Directory Structure

```
QuillStack/
├── content/
│   ├── settings.json    # Site configuration
│   ├── sitedoc.json     # Article metadata
│   ├── friends.json     # Friends links configuration
│   └── doc/             # Markdown articles directory
│       ├── 1.md
│       ├── 2.md
│       └── ...
├── src/
│   ├── app/             # Next.js App Router pages
│   │   ├── (site)/      # Main site pages
│   │   │   ├── posts/   # Article pages
│   │   │   ├── category/# Category pages
│   │   │   └── friends/ # Friends page
│   │   └── api/         # API routes (if any)
│   ├── components/      # React components
│   │   ├── site/        # Site-specific components
│   │   ├── ui/          # shadcn/ui components
│   │   └── seo/         # SEO components
│   ├── hooks/           # Custom React hooks
│   └── lib/             # Utility functions and types
├── scripts/
│   └── generate-og.tsx  # OG image generation script
├── public/              # Static assets
└── package.json
```

---

## Friends Links

The project includes a friends links system configured in [`content/friends.json`](content/friends.json).

### Configuration

```json
{
  "description": "Friends description",
  "applyInfo": {
    "title": "Apply for friendship",
    "description": "How to apply...",
    "email": "your@email.com",
    "agreement": "Agreement text"
  },
  "links": [
    {
      "id": "friend-id",
      "name": "Friend Name",
      "description": "Friend description",
      "avatar": "https://example.com/avatar.png",
      "url": "https://example.com",
      "tags": ["Tag1", "Tag2"]
    }
  ]
}
```

### Adding a Friend

1. Edit [`content/friends.json`](content/friends.json)
2. Add a new object to the `links` array
3. Save the file - the friends page will update automatically

---

## OG Image Generation

The project automatically generates Open Graph images for social media sharing during the build process. You can also generate them manually:

```bash
# Generate OG images
npm run build:og
```

### Configuration

OG image settings are in `content/settings.json` under the `ogImage` section:

```json
{
  "ogImage": {
    "slogan": "Your Slogan",
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

## Deployment

### Vercel (Recommended)

1. Fork GitHub repository
2. Go to [Vercel](https://vercel.com) and import the repository
3. Vercel will automatically detect Next.js and configure the build settings
4. Click Deploy

### Netlify

1. Fork GitHub repository
2. Go to [Netlify](https://netlify.com) and import the repository
3. Build command: `npm run build`
4. Publish directory: `out`
5. Click Deploy

---

## Notes

1. Restart the development server after modifying configuration
2. `categoryId` must match the category `id` in `settings.json`
3. Images are recommended to use CDN links, avoid putting large images in the repository
4. Publication time format: `YYYY-MM-DDTHH:mm:ss.sssZ`
5. The development server runs on port 9002: `npm run dev`

---

## License

[AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.html) - See [LICENSE](LICENSE) file for details.

> **Note**: This project is licensed under AGPL-3.0. If you use this project to provide network services, you must open-source your modifications under the same license.

---

## Treat me to a bowl of lamian

| 微信（wechat） | <img src="https://github.com/user-attachments/assets/29c0f96f-4d85-4f99-9dee-23cde279fdd1" alt="mm_reward_qrcode_1772603144418" style="zoom: 33%;" /> |
| -------------- | ------------------------------------------------------------ |

