---
title: "Interfaces that stay small"
date: 2025-05-02
draft: true
description: "Small interfaces are easier to replace, easier to test, and harder to misuse."
---

The best interface is usually the one that refuses to describe everything it knows. It should expose the operation the caller needs, not the data model the implementation happens to use today.

For example, prefer a narrow operation:

```go
type TokenStore interface {
	Issue(ctx context.Context, userID string) (Token, error)
	Revoke(ctx context.Context, tokenID string) error
}
```

over passing a repository through every layer and letting each caller assemble its own behaviour.

## Pressure To Grow

Interfaces tend to grow when they become convenient dumping grounds. A good test is whether every method has the same reason to change. If it does not, split it.

That keeps the call site honest and makes replacement work less dramatic later.

