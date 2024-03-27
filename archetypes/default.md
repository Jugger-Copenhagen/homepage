---
title: {{ replace .File.ContentBaseName "-" " " | title }}
menu_title: {{ index (split .File.ContentBaseName "-") 0 | string | title }}
description: 
date: {{ .Date }}
draft: true
weight: 10
---
