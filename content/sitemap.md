---
title: "Sitemap"
date: 2026-01-05
draft: false
---

# Sitemap

A complete overview of all content on ByteCascade.

### Main Pages
- [Home](/)
- [All Posts](/posts/)
- [Categories](/categories/)
- [Tags](/tags/)

### Static Pages
{{ range where .Site.RegularPages "Section" "==" "" }}
- [{{ .Title }}]({{ .Permalink }})
{{ end }}

### Blog Posts
{{ range where .Site.RegularPages "Section" "posts" }}
- [{{ .Title }}]({{ .Permalink }}) — {{ dateFormat "January 2, 2006" .Date }}
{{ end }}

### Categories
{{ range .Site.Taxonomies.categories }}
- [{{ .Page.Title }} ({{ .Count }} posts)]({{ .Page.Permalink }})
{{ end }}

### Tags
{{ range .Site.Taxonomies.tags }}
- [{{ .Page.Title }} ({{ .Count }} posts)]({{ .Page.Permalink }})
{{ end }}
