---
title: "Debugging by reducing the search space"
date: 2025-05-12
draft: true
description: "A practical note on shrinking unknowns until the failure has nowhere left to hide."
---

Most debugging gets easier once the problem is smaller. The first useful move is often not to understand the whole system, but to remove everything that is probably not involved.

The shape is simple:

1. Reproduce the failure.
2. Remove one variable.
3. Run the smallest check that could disprove your current theory.
4. Keep the result, even when it is boring.

## Keep Notes

Write down the checks as you make them. A plain text scratch file is enough:

```text
10:14 fails with cache enabled
10:19 passes with cache disabled
10:27 fails when cache key includes tenant id
```

This makes it harder to circle back through the same theory twice.

> The goal is not cleverness. The goal is a smaller problem than the one you started with.

