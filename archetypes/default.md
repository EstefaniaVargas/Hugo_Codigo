<!-- Template de los markdown que están en content. Este define que propiedades aparecerá en todos los md por defecto -->

---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
---

