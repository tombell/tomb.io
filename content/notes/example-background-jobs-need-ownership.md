---
title: "Background jobs need ownership"
date: 2025-03-03
draft: true
description: "Queues do not remove product responsibility. They just move work out of the request path."
---

Background jobs are easy to create and easy to neglect. Once work is asynchronous, failures become quieter unless the system gives them a clear owner.

Every recurring job should answer a few questions:

1. What user-visible promise does this job support?
2. How late can it run before anyone cares?
3. Who gets paged when it stops making progress?
4. Is retrying safe?

## Make Progress Observable

A job does not need a dashboard on day one, but it does need a small set of useful signals.

```ruby
class RefreshSearchIndexJob
  retry_on Search::RateLimited, wait: :exponentially_longer, attempts: 8

  def perform(account_id)
    account = Account.find(account_id)
    Search::Indexer.refresh!(account)
  end
end
```

For code like this, the useful signals are not just failures. You also want age of oldest queued job, retry count, and last successful refresh per account.

> Async work is still product work. Treat it like a promise, not a cleanup task.
