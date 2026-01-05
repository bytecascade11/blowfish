---
title: "Sitemap"
date: 2026-01-05
draft: false
---

# Sitemap

A complete list of all pages and posts on ByteCascade.

{{< rawhtml >}}
<ul>
  <li><a href="/">Home</a></li>
  <li><a href="/posts/">All Posts</a></li>
  <li><a href="/categories/">Categories</a></li>
  <li><a href="/tags/">Tags</a></li>
  {{ range .Site.RegularPages }}
    <li><a href="{{ .RelPermalink }}">{{ .Title }}</a></li>
  {{ end }}
  {{ range .Site.Sections }}
    <li><strong>{{ .Title }}</strong>
      <ul>
        {{ range .Pages }}
          <li><a href="{{ .RelPermalink }}">{{ .Title }}</a></li>
        {{ end }}
      </ul>
    </li>
  {{ end }}
</ul>
{{< /rawhtml >}}
