---
learning_level: "Intermediate"
prerequisites: ["Failure Models (Part 1)", "Basic understanding of distributed systems"]
estimated_time: "25 minutes"
learning_objectives:
  - "Apply failure recovery strategies to system design"
  - "Design systems that gracefully handle failures"
  - "Implement patterns for failure isolation and recovery"
related_topics:
  prerequisites:
    - ./04_failure-models.md
  builds_upon:
    - ./04_failure-models.md
  enables:
    - ../04_principles/05_fault-tolerance.md
    - ../08_failures/01_introduction.md
  cross_refs: []
---

# Failure Models (Part 2): Recovery Strategies and Design Patterns

## Failure Recovery Strategies

### 1. Retry with Exponential Backoff

**When to use**: Transient failures (network glitches, temporary overload).

**How it works**:
- Retry failed operation
- Wait longer between each retry (exponential backoff)
- Give up after max attempts

**Example**: API call fails → wait 1s → retry → wait 2s → retry → wait 4s → retry.

**Trade-offs**:
- ✅ Handles transient failures automatically
- ❌ Can amplify load if many retries
- ❌ Must distinguish transient vs permanent failures

### 2. Circuit Breaker

**When to use**: Repeated failures from a dependency.

**How it works**:
- Track failure rate
- If threshold exceeded, "open" circuit (stop calling)
- After timeout, "half-open" (test if fixed)
- If successful, "close" circuit (resume normal operation)

**Example**: Database repeatedly timing out → stop sending queries → test after 30s → resume if healthy.

**Trade-offs**:
- ✅ Prevents cascade failures
- ✅ Fails fast instead of waiting
- ⚠️ Requires careful tuning of thresholds

### 3. Graceful Degradation

**When to use**: Non-critical features failing.

**How it works**:
- Disable failing feature
- Continue serving core functionality
- Return cached data or simplified responses

**Example**: Recommendation service down → show default recommendations instead of failing entire page.

**Trade-offs**:
- ✅ Better user experience than complete failure
- ✅ System remains usable
- ❌ Reduced functionality

### 4. Failover

**When to use**: Primary component fails, need backup.

**How it works**:
- Detect primary failure
- Switch traffic to backup/replica
- Restore primary when fixed

**Example**: Primary database fails → route reads to read replica → promote replica to primary.

**Trade-offs**:
- ✅ Maintains service during failures
- ✅ Transparent to users
- ❌ Failover time (brief downtime)
- ❌ Data synchronization complexity

## Designing for Failure

### Principles

1. **Assume failures will happen**: Design defensively
2. **Fail fast**: Detect and handle failures quickly
3. **Isolate failures**: Prevent cascade failures
4. **Plan recovery**: Know how to restore service
5. **Monitor everything**: Detect failures before users notice

### Common Patterns

**Redundancy**: Multiple instances of critical components.

**Idempotency**: Operations safe to retry.

**Stateless design**: Easier to recover (no state to restore).

**Timeouts**: Don't wait forever for responses.

**Rate limiting**: Prevent overload from causing failures.

## Key Takeaways

1. **Failures are normal** - design expecting them
2. **Different failure types** require different strategies
3. **Detect failures quickly** - use heartbeats, health checks, timeouts
4. **Recover gracefully** - retry, circuit break, degrade, failover
5. **Isolate failures** - prevent cascade effects

---

*Previous: [Failure Models (Part 1)](./04_failure-models.md)*  
*Next: Learn about [Fault Tolerance](../04_principles/05_fault-tolerance.md) or explore [Failure Analysis](../08_failures/01_introduction.md).*

