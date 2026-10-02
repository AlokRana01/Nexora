# Performance Engineering Rules

Performance claims must be evidence-based.

---

## 1. Never Assume Something Is Slow

Measure it.

---

## 2. Establish a Baseline

Before optimizing, measure the relevant metric.

Examples:

- Startup time
- Page load time
- Function execution time
- Memory usage
- Dataset processing time
- Model training time
- Inference latency

---

## 3. Identify the Bottleneck

Do not optimize random code.

Determine where the actual cost occurs.

Use:

- Profiling
- Timing
- Logs
- Metrics
- Runtime inspection

---

## 4. Change One Important Variable at a Time

When practical, isolate performance changes so their effect can be measured.

---

## 5. Measure After the Change

Compare:

BEFORE
vs.
AFTER

Do not claim improvement without measurement.

---

## 6. Caching

Before adding caching:

Understand:

- What is expensive
- Whether the result is deterministic
- Cache lifetime
- Cache invalidation
- Memory implications
- User/session isolation

Never cache user-specific or mutable data incorrectly.

---

## 7. Avoid Premature Optimization

Do not complicate architecture for hypothetical performance problems.

Optimize verified bottlenecks.

---

## 8. Performance Report

When optimization is performed, report:

### Baseline
Measured before change.

### Change
What was modified.

### Result
Measured after change.

### Trade-offs
Memory, complexity, correctness, or maintainability implications.

---

## 9. No Fake Numbers

Never invent:

- Load times
- Speed improvements
- Memory reductions
- Throughput
- Accuracy improvements

Only report measured values.