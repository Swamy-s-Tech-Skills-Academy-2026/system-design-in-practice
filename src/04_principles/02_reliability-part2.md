---
learning_level: "Intermediate"
prerequisites: ["Reliability (Part 1)", "Understanding of availability"]
estimated_time: "25 minutes"
learning_objectives:
  - "Apply testing strategies for reliability"
  - "Understand monitoring and observability for reliability"
  - "Design systems with reliability as a first-class concern"
related_topics:
  prerequisites:
    - ./02_reliability.md
  builds_upon:
    - ./02_reliability.md
  enables:
    - ./05_fault-tolerance.md
    - ../05_building-blocks/07_monitoring.md
  cross_refs: []
---

# Reliability (Part 2): Testing and Monitoring

## Testing for Reliability

### 1. Unit Testing

**Purpose**: Test individual components in isolation.

**Focus**:
- Correctness of logic
- Edge cases
- Error handling

**Example**: Test payment calculation with various inputs.

### 2. Integration Testing

**Purpose**: Test interactions between components.

**Focus**:
- API contracts
- Data flow
- Error propagation

**Example**: Test payment service calling user service and database.

### 3. Chaos Engineering

**Purpose**: Test system behavior under failure conditions.

**Techniques**:
- Inject failures (kill processes, drop network)
- Simulate load spikes
- Test recovery mechanisms

**Example**: Randomly kill database connections to test retry logic.

### 4. Load Testing

**Purpose**: Test system under expected and peak loads.

**Focus**:
- Performance degradation
- Resource exhaustion
- Error rates under load

**Example**: Simulate 10x normal traffic to find breaking points.

## Monitoring for Reliability

### Key Metrics

**Error Rate**: Percentage of failed requests
- Target: < 0.1%
- Alert: > 1%

**Latency**: Response time distribution
- Track: p50, p95, p99
- Alert: p99 > SLA threshold

**Throughput**: Requests per second
- Monitor: Trends, capacity limits
- Alert: Sudden drops

**Resource Usage**: CPU, memory, disk
- Monitor: Trends, capacity
- Alert: Approaching limits

### Observability

**Logging**: Record events for debugging
- Structured logs (JSON)
- Appropriate log levels
- Include context (request ID, user ID)

**Tracing**: Track requests across services
- Distributed tracing
- Identify bottlenecks
- Understand failure paths

**Metrics**: Quantitative measurements
- Counters, gauges, histograms
- Time-series data
- Dashboards and alerts

## Reliability Patterns in Practice

### Pattern 1: Health Checks

**Implementation**: Endpoint that reports system health.

```python
@app.get("/health")
def health_check():
    checks = {
        "database": check_database(),
        "cache": check_cache(),
        "external_api": check_external_api()
    }
    if all(checks.values()):
        return {"status": "healthy"}
    return {"status": "unhealthy", "checks": checks}, 503
```

**Use**: Load balancers, orchestration systems, monitoring.

### Pattern 2: Retry Logic

**Implementation**: Retry transient failures with backoff.

```python
def call_service_with_retry(max_retries=3):
    for attempt in range(max_retries):
        try:
            return service.call()
        except TransientError:
            if attempt < max_retries - 1:
                time.sleep(2 ** attempt)  # Exponential backoff
            else:
                raise
```

**Use**: Network calls, database operations, external APIs.

### Pattern 3: Circuit Breaker

**Implementation**: Stop calling failing service.

```python
class CircuitBreaker:
    def __init__(self, failure_threshold=5):
        self.failures = 0
        self.threshold = failure_threshold
        self.state = "closed"
    
    def call(self, func):
        if self.state == "open":
            raise CircuitOpenError()
        try:
            result = func()
            self.failures = 0
            return result
        except Exception:
            self.failures += 1
            if self.failures >= self.threshold:
                self.state = "open"
            raise
```

**Use**: External dependencies, repeated failures.

## Key Takeaways

1. **Test failure scenarios** - chaos engineering reveals weaknesses
2. **Monitor everything** - metrics, logs, traces
3. **Set clear targets** - error rates, latency SLAs
4. **Automate recovery** - retry, circuit breakers, failover
5. **Learn from failures** - post-mortems, continuous improvement

---

*Previous: [Reliability (Part 1)](./02_reliability.md)*  
*Next: Learn about [Fault Tolerance](./05_fault-tolerance.md) or explore [Monitoring](../05_building-blocks/07_monitoring.md).*
