# QuillStack

👋👋🏻👋🏼👋🏽👋🏾👋🏿

Hello, welcome to QuillStack! This is a NextJS project initiated by SnowBall (@SnowBall-Bqiu).

[Commit History](https://github.com/QuillStack-Blog/QuillStack/commits/main)

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
| `heroImageUrl` | Homepage Banner Image | `"https://example.com/hero.jpg"` |

#### Author Information (`author`)

| Field | Description |
| ----------- | -------- |
| `name` | Author Name |
| `avatarUrl` | Author Avatar |

#### Pagination Settings (`pagination`)

| Field | Description | Default Value |
| -------------- | -------------- | ------ |
| `postsPerPage` | Number of posts per page | `10` |

#### Navigation Menu (`navigation`)

```json
"navigation": [
  { "id": "1", "label": "Home", "href": "/" },
  { "id": "2", "label": "Friends", "href": "https://example.com/friends" }
]
```

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

Contains footer text, brand information, social links, and link groups.

#### Theme Configuration (`theme`)

| Field | Description | Example |
| -------------- | -------- | ----------------- |
| `bodyFont` | Body font | `"PT Sans"` |
| `headlineFont` | Headline font | `"Space Grotesk"` |

#### SEO Configuration (`seo`)

| Field | Description |
| --------------- | -------------- |
| `siteUrl` | Official website domain |
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
static-blog-dev/
├── content/
│   ├── settings.json    # Site configuration
│   ├── sitedoc.json     # Article metadata
│   └── doc/             # Markdown articles directory
│       ├── 1.md
│       ├── 2.md
│       └── ...
├── src/
│   ├── app/             # Next.js pages
│   ├── components/      # React components
│   └── lib/             # Utility functions
├── public/              # Static assets
└── package.json
```

---

## Notes

1. Restart the development server after modifying configuration
2. `categoryId` must match the category `id` in `settings.json`
3. Images are recommended to use CDN links, avoid putting large images in the repository
4. Publication time format: `YYYY-MM-DDTHH:mm:ss.sssZ`