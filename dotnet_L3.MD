# Transaction Failures & Retry Mechanisms

Q1: During a transaction process, if a transaction fails,
how do you figure it out and make sure it gets reprocessed?

Scenario:
In a financial system, a customer initiates a fund transfer.
Due to a network failure or database timeout, the transaction fails.
How do you ensure it retries automatically without duplication?

The best approach is to use a retry mechanism with idempotency. This can be done via:

**- Implementing a retry policy using Polly:**

```
var retryPolicy = Policy
.Handle<Exception>()
.WaitAndRetry(3, retryAttempt = TimeSpan. FromSeconds(retryAttempt));

retryPolicy.Execute(() = ProcessTransaction(transactionId));
```

* Retries up to 3 times before failing.
* Uses exponential backoff to prevent overload.

**- Using a background job queue (Hangfire, Quartz.NET, or MassTransit):**

2) Using a background job queue (Hangfire, Quartz.NET, or MassTransit) :

* Failed transactions can be pushed to a retry queue for delayed processing.
* The background job polls the queue and retries processing.

**- Database-based tracking:**

3) Database-based tracking:

* Store transactions in a table with a "processing" status.
* If a failure occurs, update the status and retry later.
* Ensures idempotency by checking if the transaction has already been processed before re-executing.

# 2. Deadlocks in SQL Transactions

Q2: In a high-volume transaction system, deadlocks occur frequently.
How do you resolve and prevent them?

Scenario:
Multiple services in a banking system update the customer balance simultaneously.
This leads to frequent deadlocks in SQL.

**- Use a consistent ordering of operations:**

1) Use a consistent ordering of operations:

```
BEGIN TRANSACTION
UPDATE AccountBalance SET Balance = Balance - @amount WHERE AccountId = @sender
UPDATE AccountBalance SET Balance = Balance + @amount WHERE AccountId = @receiver
COMMIT
```

* Always debit before credit to prevent deadlocks.

**- Lower the lock scope:**

2) Lower the lock scope:

Instead of SERIALIZABLE, use READ COMMITTED or SNAPSHOT.

**- Retry logic in case of deadlock:**

3) Retry logic in case of deadlock:

var retryPolicy = Policy.Handle `<SqlException>`(ex = ex.Number = 1205)
.Retry(3);
retryPolicy. Execute(() =ExecuteTransaction());
