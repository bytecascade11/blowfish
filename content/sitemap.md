---
title: "Sitemap"
date: 2026-01-05
draft: false
---

# Sitemap

Explore all content on ByteCascade.

## Main Navigation
- [Home](/)
- [Posts](/posts/)
- [Categories](/categories/)
- [Tags](/tags/)

## Information Pages
{{ range where .Site.RegularPages "Section" "==" "" }}
- [{{ .Title }}]({{ .Permalink }})
{{ end }}

## Latest Articles
{{ range first 20 (where .Site.RegularPages "Section" "posts") }}
- [{{ .Title }}]({{ .Permalink }}) <small>{{ dateFormat "Jan 2, 2006" .Date }} • {{ .ReadingTime }} min read</small>
{{ end }}

{{ if gt (len .Site.RegularPages) 20 }}
- [View all posts](/posts/)
{{ end }}

## Categories
{{ range .Site.Taxonomies.categories }}
- [{{ .Page.Title }}]({{ .Page.Permalink }}) <small>({{ .Count }} articles)</small>
{{ end }}

## Tags
{{ range .Site.Taxonomies.tags }}
- [{{ .Page.Title }}]({{ .Page.Permalink }}) <small>({{ .Count }} articles)</small>
{{ end }}
