# My Personal Blog

A personal blog built with [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme. Posts cover software engineering topics including web development, React, and ML/AI.

🌐 **Live site:** [omarshabana.me](https://omarshabana.me/)

---

## About

Hi, I'm Omar — a Software Engineer from Egypt interested in web development, mobile development, and ML/AI. This blog is where I share my thoughts, learnings, and technical deep-dives.

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| [Hugo](https://gohugo.io/) | Static site generator |
| [PaperMod](https://github.com/adityatelange/hugo-PaperMod) | Hugo theme (via git submodule) |
| [Netlify](https://www.netlify.com/) | Hosting & deployment |

---

## Getting Started

### Prerequisites

- [Hugo](https://gohugo.io/installation/) (extended version recommended)
- [Git](https://git-scm.com/)

### Clone the Repository

```sh
git clone --recurse-submodules https://github.com/Mirohhh/<repo-name>.git
cd <repo-name>
```

> **Note:** The `--recurse-submodules` flag is required to pull in the PaperMod theme.

If you already cloned without the flag, run:

```sh
git submodule update --init --recursive
```

### Run Locally

```sh
hugo server -D
```

Then open [http://localhost:1313](http://localhost:1313) in your browser. The `-D` flag includes draft posts.

### Build for Production

```sh
hugo
```

The generated site will be in the `public/` directory.

---

## Project Structure

```
.
├── archetypes/         # Content templates
├── assets/             # Unprocessed assets (JS, CSS, images)
├── content/
│   └── posts/          # Blog posts (Markdown)
├── data/               # Data files
├── i18n/               # Internationalization files
├── layouts/            # Custom layout overrides
├── static/             # Static files served as-is
├── themes/
│   └── PaperMod/       # Theme (git submodule)
└── hugo.yaml           # Site configuration
```

---

## Writing a New Post

```sh
hugo new posts/my-new-post.md
```

This creates a new Markdown file in `content/posts/` using the default archetype. Set `draft: false` in the front matter when the post is ready to publish.

### Front Matter Example

```yaml
---
title: "My Post Title"
date: 2026-01-01
draft: false
author: "Omar Shabana"
tags: ["Web Dev", "React"]
---
```

---

## Configuration

Site settings are managed in `hugo.yaml`. Key options include:

- **`baseURL`** — The live URL of the site
- **`title`** — The site title
- **`params.homeInfoParams`** — The welcome message on the homepage
- **`params.socialIcons`** — Links to social profiles

---

## Connect

- **GitHub:** [@Mirohhh](https://github.com/Mirohhh)
- **LinkedIn:** [Omar Shabana](www.linkedin.com/in/omar-shabana11)

---

## License

This blog's content is personal and all rights are reserved. The PaperMod theme is licensed under the [MIT License](https://github.com/adityatelange/hugo-PaperMod/blob/master/LICENSE).
