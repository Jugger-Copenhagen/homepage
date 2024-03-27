---
title: ''           # Enter long title manually.
params:
    shortitle: {{ index (split .File.ContentBaseName "-") 0 | string }}   # The short title or abbreviation
    begin: 2024-08-28T09:00:00+01:00   # Placeholder for beginning day of the event, possibly with time and timezone
    end: 2024-08-28T09:00:00+01:00     # End date and time of the event.
description: ''     # Event description in one sentence. Possibly the long title.
date: {{ .Date }}   # Creation date of this page.
draft: true
---