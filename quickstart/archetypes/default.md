---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
---

<nav class="sidebar-nav">
    {{ $currentPage := . }}
    {{ range .Site.Menus.main }}
    <a class="sidebar-nav-item{{if or ($currentPage.IsMenuCurrent "main" .) ($currentPage.HasMenuCurrent "main" .) }} active{{end}}" href="{{ .URL }}" title="{{ .Title }}">{{ .Name }}</a>
    {{ end }}
</nav>