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

### Expand code block example below:

<details>

```
module "demo" {
  source = "github.com/my-repo/demo"

  name = "whatever variable you would like to pass"

  tags {
    "Environment" = "${var.environment}"
  }
}
```
</details>