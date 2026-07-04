---
title: "Observability without theatre"
date: 2025-03-28
draft: true
description: "Signals should answer operational questions, not decorate a dashboard."
---

Dashboards are cheap to create and expensive to trust. A useful signal starts from a question someone might ask during an incident.

Examples:

- Are requests failing for every tenant or one tenant?
- Did latency move at the edge, the application, or the database?
- Is the queue draining?
- Which version introduced the change?

## Name The Decision

Every chart should support a decision. If the decision is not clear, the chart probably belongs in a notebook, not an operational dashboard.

Inline values like `p95`, `error_rate`, and `queue_depth` are useful only when the surrounding context says what they mean.

