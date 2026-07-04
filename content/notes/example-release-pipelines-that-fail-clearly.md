---
title: "Release pipelines that fail clearly"
date: 2025-04-11
draft: true
description: "A release pipeline should make the next action obvious when something breaks."
---

A pipeline failure is only useful if it tells the person on call what to do next. Red output is not enough.

Good failures have a few properties:

- The failing step has a name that matches the deployment stage.
- The log points to the command that failed.
- The recovery path is linked or obvious.
- Retryable and non-retryable failures look different.

## Example

```sh
hugo --gc --minify
```

If that command fails, the pipeline should show whether the issue is content, templates, generated assets, or the build environment.

Clear failures reduce coordination cost. They also make releases less dependent on the one person who remembers how the pipeline works.

