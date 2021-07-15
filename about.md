---
layout: page
title: About
permalink: /about/
---

This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](https://jekyllrb.com/)


----
You can find the source code for Minima at GitHub:
[jekyll](jekyll-organization) /
[minima](https://github.com/jekyll/minima)

You can find the source code for Jekyll at GitHub:
[jekyll](jekyll-organization) /
[jekyll](https://github.com/jekyll/jekyll)

----
[~~jekyll-organization~~ Double tagged to strikethru ;)](https://github.com/jekyll)

| Effect        | Format          |   |   |   |
|---------------|-----------------|---|---|---|
| strikethrough | ~strikethrough~ |   |   |   |
| bold          | __bold__        |   |   |   |
| italics       | _italics_       |   |   |   |
|               |                 |   |   |   |

<details>
  <summary><em><strong>Expand code block</strong></em></summary>

```yaml
trigger:
  batch: true
  branches:
    include:
    - main
  paths:
    include:
      - AzureAD/Subscriptions/

schedules:
- cron: "0 */1 * * *"
  displayName: Run hourly every day
  branches:
    include:
    - main
  always: true

pr: none

extends:
  template: ../Shared/azure-pipelines.yml
```

</details>