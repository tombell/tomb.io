---
title: "Latency budgets as design tools"
date: 2025-04-23
draft: true
description: "A latency budget is a design constraint, not just a dashboard threshold."
---

Latency budgets are useful before anything ships. They force decisions about what the interface can afford to do synchronously, what needs to be cached, and what should move out of the request path.

```text
request budget: 250ms
network edge:    35ms
auth/session:    20ms
database read:   80ms
render:          45ms
margin:          70ms
```

The numbers do not need to be perfect. They need to be concrete enough to make tradeoffs visible.

## Useful Questions

- What can be stale for 30 seconds?
- What can be computed after the response?
- What query shape would make this budget impossible?

Once the budget exists, performance work becomes less vague.

