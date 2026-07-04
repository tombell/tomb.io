---
title: "Configuration that explains itself"
date: 2025-03-17
draft: true
description: "Config is part of the interface. Name it like someone will debug it at 02:00."
---

Configuration tends to become archaeology. A setting is added for a migration, an incident, or a customer exception, then survives long after the original context is gone.

Good configuration should make three things clear:

- What behaviour changes.
- Who should change it.
- What happens when it is wrong.

## Prefer Specific Names

Avoid names that describe implementation details without describing the decision:

```toml
# vague
enable_fast_path = true

# clearer
serve_cached_profile_pages = true
```

The second name is longer, but it gives the next person a useful mental model.

Short names are only better when they preserve meaning.

## Leave Edges Visible

Document the dangerous values near the value itself. A comment in the same file beats a paragraph in a runbook nobody opens during an incident.

